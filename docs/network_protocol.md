# Network Protocol

How the Silkroad Online client communicates with game servers.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
  - [Server Types](#server-types)
  - [Connection Flow](#connection-flow)
  - [Class Hierarchy](#class-hierarchy)
  - [Source Files](#source-files)
- [Packet Structure](#packet-structure)
  - [Header Format](#header-format)
  - [Massive Packets](#massive-packets)
  - [Message Stream Buffer](#message-stream-buffer)
- [Security Layer](#security-layer)
  - [Handshake Sequence](#handshake-sequence)
  - [Security Modes](#security-modes)
  - [Blowfish Packet Encryption](#blowfish-packet-encryption)
  - [Security Counter (CRC)](#security-counter-crc)
  - [Server Signature Exchange](#server-signature-exchange)
- [Opcode Reference](#opcode-reference)
  - [Opcode Groups](#opcode-groups)
  - [Known Opcodes](#known-opcodes)
- [Message Dispatch](#message-dispatch)
  - [CNetProcessIn Handlers](#cnetprocessin-handlers)
- [Configuration Files](#configuration-files)
- [Binary Analysis Reference](#binary-analysis-reference)

## Overview

Silkroad Online uses a custom TCP-based protocol over Winsock2 (WS2_32.dll) with asynchronous overlapped I/O via IOCP (I/O Completion Ports). All packets share a 6-byte header containing size, opcode, and security bytes. An optional Blowfish encryption layer and CRC counter protect the data payload after the initial handshake.

The client connects to three server types in sequence: Gateway (login/server selection), Agent (gameplay), and Download (patching).

## Architecture

### Server Types

| Server | Purpose | Config Source |
|--------|---------|---------------|
| `GatewayServer` | Login authentication, server list, character selection | `gateport.txt`, `divisioninfo.txt` |
| `AgentServer` | Gameplay: movement, combat, chat, items, skills | Assigned by Gateway after login |
| `DownloadServer` | Patch distribution, file updates | Assigned by Gateway if update needed |

### Connection Flow

```
1. Client reads gateport.txt → gets Gateway IP:port
2. Client reads divisioninfo.txt → gets server division list
3. Client connects to GatewayServer
4. Server sends Handshake Setup (opcode 0x5000)
5. Client responds with Handshake Response (opcode 0x9000)
6. Security layer established (Blowfish + CRC)
7. Client sends Login (opcode 0x2001)
8. Server responds with server list / character data
9. Client disconnects from Gateway, connects to AgentServer
10. Repeat handshake on Agent connection
11. Gameplay packets flow on Agent connection
```

### Class Hierarchy

Reconstructed from RTTI data in `sro_client.exe`:

```
CNetEngine                    — Top-level network engine
├── CSession                  — Session management, send/receive
│   ├── CBaseSocket           — Socket abstraction
│   │   ├── CRTSocket         — Runtime socket implementation
│   │   └── CSockStream       — Stream socket (TCP)
│   │       └── CSockListener — Listening socket (server-side)
│   └── CBlowFish             — Per-session Blowfish cipher
├── CClientNet                — Client network interface
│   └── CClientProcess        — Client-side processing
├── CPeerProcessIOCP          — IOCP worker thread
├── CPeerProcessOverlapped    — Overlapped I/O handler
├── CNetProcessIn             — Inbound message processor
│   ├── CNetProcessSecond     — Secondary processing stage
│   └── CNetProcessThird      — Tertiary processing stage
├── CMsgHandler               — Message handler base
├── CMsgHooker                — Message hook system
├── CMsgStreamBuffer          — Message serialization buffer
├── CMsg                      — Individual message object
├── CMassiveMsg               — Multi-part message container
├── CKeySender                — Key/input transmission
├── CUdpPingClient            — UDP ping for latency measurement
└── CInterfaceNetSender       — UI-to-network bridge
```

Additional transport classes:
- `CUdpPingBase` / `CUdpPingServer` — Server-side UDP ping
- `CSockDatagram` — UDP datagram socket wrapper
- `CFileTransMgr<CUncompZlib, CPackerFM>` — File transfer with zlib compression
- `CIDPool` — Session/connection ID management
- `CEventHandler`, `CTask` — Async event and task management

### Source Files

Debug strings reveal the original source tree at `D:\vss-od\Silkroad\Client\client\`:

| Source File | Purpose |
|-------------|---------|
| `Client.cpp` | Main client entry |
| `MsgStreamBuffer.h` | Message serialization (header: `EngineCommon/IMemory.h`) |
| `InterfaceNetSender.cpp` | UI action → network message translation |
| `GInterfaceSend.cpp` | General interface send operations |
| `NetProcessInInner.cpp` | Core inbound message processing |
| `NetProcessInInterface.cpp` | UI-related inbound messages |
| `NetProcessInNavAndSkill.cpp` | Navigation and skill messages |
| `NetProcessInObject.cpp` | Object/entity state updates |
| `massivemsg.cpp` | Multi-part message assembly (uses zlib 1.1.4) |
| `thread\threadmanager.cpp` | Worker thread management |

## Packet Structure

### Header Format

Every packet has a fixed 6-byte header followed by variable-length data:

```
Offset  Size  Type  Field
0x00    2     u16   data_size        (LE; bit 15 = massive flag)
0x02    2     u16   opcode           (LE; message ID)
0x04    1     u8    security_count   (rolling counter, 0 if CRC disabled)
0x05    1     u8    security_crc     (checksum byte, 0 if CRC disabled)
0x06    ...   u8[]  data[data_size & 0x7FFF]
```

**Total packet size** = `(data_size & 0x7FFF) + 6`

The `data_size` field holds the byte count of the payload following the 6-byte header. The actual data size is masked with `0x7FFF` (15 bits), giving a maximum single-packet payload of 32,767 bytes.

**Evidence:** At VA `0x004B0D90`, the send path reads the data size pointer, masks with `0x7FFF`, and adds 6 to compute the total packet size:

```asm
mov  edx, [eax+0x1054]      ; data size pointer
movzx edx, word [edx]
and  edx, 0x7FFF            ; clear massive flag
add  edx, 6                 ; total = data + 6-byte header
```

### Massive Packets

When bit 15 (`0x8000`) of the `data_size` field is set, the packet is a **massive packet** — a multi-part message that spans multiple physical packets. The `CMassiveMsg` class reassembles these using an internal message list (`m_MsgList`). Massive messages use zlib compression (version `"1.1.4"` embedded in binary).

The encryption path checks and clears this flag:
```asm
test word [ecx], 0x8000     ; check massive flag in size field
...
and  word [eax], 0x7FFF     ; clear the flag after processing
```

### Message Stream Buffer

The `CMsgStreamBuffer` class provides cursor-based read/write access to packet data:

```
Debug format: "MSGID:0x%X,R(%d),W(%d),T(%d)"
  MSGID = opcode
  R     = read cursor position  (session offset +0x103C, u16)
  W     = write cursor position (session offset +0x103E, u16)
  T     = total buffer size
```

Data is read sequentially using typed read functions that advance the read cursor. The read functions perform bounds checking (read position must not exceed write position). Key functions:

| Function (VA) | Operation |
|---------------|-----------|
| `0x004B3B40` | Read 1 byte (flags/type) from data buffer |
| `0x004AF830` | Read N bytes (bulk data copy) from data buffer |
| `0x004B3BA0` | Read u32 value |
| `0x004B3C00` | Read variable-length data block |

## Security Layer

### Handshake Sequence

Before any game messages can be exchanged, the server initiates a security handshake:

```
Server ──[0x5000 Handshake Setup]──> Client
  │
  │  Contains: security_flags, [blowfish_seed], [crc_seeds], [signature]
  │
Client ──[0x9000 Handshake Response]──> Server
  │
  │  Contains: client acknowledgment, [signature response]
  │
  ╰──── Security layer now active ────╯
```

The handshake function is `_OnMsgReceivedBeforeHandshake()` at VA `0x004B1DA0`. It first verifies the incoming opcode is `0x5000`, then processes the security setup fields in order:

```
1. Read security_flags (u8)
2. If flags & 0x02: read 8-byte Blowfish key seed → initialize session cipher
3. If flags & 0x04: read CRC seed values → initialize security counters
4. If flags & 0x10: read server signature → verify and exchange signatures
5. Write response opcode 0x9000 into outgoing packet
6. Send response back to server
```

Error logging reveals the handshake states:

| Debug String | Meaning |
|-------------|---------|
| `"Initialize [MsgID: 0x%x]"` | Handshake initialization started |
| `"Handshake ServerSignature Error"` | Signature verification failed |
| `"Handshake Failed:%d"` | Handshake failed with error code |
| `"Handshake Recipient Size:%d"` | Unexpected recipient data size |
| `"Handshake RecipientInfo Error"` | Invalid recipient information |
| `"SecurityModeCheck - Mode:%d, Handshake:%d"` | Security mode validation |

### Security Modes

The security mode byte controls which protection layers are active:

| Bit | Mask | Feature | Description |
|-----|------|---------|-------------|
| 0 | `0x01` | Session type | Distinguishes session types |
| 1 | `0x02` | Blowfish encryption | Encrypt/decrypt packet data payload |
| 2 | `0x04` | CRC counter | Rolling security counter and checksum |
| 3 | `0x08` | Extended check | Additional security validation |
| 4 | `0x10` | Server signature | Signature exchange during handshake |

The security setup function at VA `0x004B0CC0` reads these flags and initializes the corresponding subsystems. The mode byte is stored at session offset `+0x016F`.

The `0x9000` handler at VA `0x004B22B0` validates mode consistency by checking multiple flag combinations before allowing the handshake response.

### Blowfish Packet Encryption

When encryption is enabled (security flag bit 1), the packet **data payload** (bytes 6+ after the header) is encrypted with Blowfish in ECB mode. Each session has its own `CBlowFish` instance at session object offset `+0x0158`.

The session Blowfish key is derived from the 8-byte seed sent in the handshake `0x5000` packet:

```asm
; At VA 0x004B0CE0 — copy 8-byte key seed to session's CBlowFish
push 8                       ; key length
lea  ecx, [edi+0x0C]        ; source: 8-byte seed from handshake packet
push ecx
lea  ecx, [esi+0x158]       ; destination: session's CBlowFish instance
call SetKey                  ; VA 0x004AA4C0
```

This per-session key is distinct from the PK2 archive key. Both use the same `CBlowFish` implementation with **little-endian** u32 byte ordering (see [PK2 Format: Encryption Key](pk2_format.md#encryption-key)).

Debug strings for encryption errors:
- `"encryption fail"` — decryption of incoming packet failed
- `"Encryption"` — logged with MSGID when encrypted packet has massive flag set

### Security Counter (CRC)

When CRC is enabled (security flag bit 2), header bytes 4-5 carry a rolling security counter and checksum to detect packet tampering or replay.

**Initialization:**

The seed (from handshake, or default `0x9ABFB3B6` if none provided) is processed through an LFSR-based PRNG four times. Results are XORed to produce three seed bytes:

| Session Offset | Name | Purpose |
|---------------|------|---------|
| `+0x016C` | seed1 | Primary counter byte |
| `+0x016D` | seed2 | Secondary counter byte |
| `+0x016E` | seed3 | Tertiary counter byte |

**LFSR PRNG** (VA `0x004AFB80`, 32 iterations per call):

```python
def prng_next(seed):
    """One call to the LFSR PRNG — advances seed by 32 steps."""
    for _ in range(32):
        tmp = seed
        tmp = (tmp >> 2) ^ tmp
        tmp = (tmp >> 2) ^ tmp
        tmp = (tmp >> 1) ^ tmp
        tmp = (tmp >> 1) ^ tmp
        tmp = (tmp >> 1) ^ tmp
        bit = ((seed >> 1) ^ tmp) & 1
        seed = (seed & 0xFFFFFFFE) | bit
    return seed & 0xFFFFFFFF
```

**Per-packet counter update** (VA `0x004B0DB0`):

```python
def compute_security_bytes(seed1, seed2, seed3):
    """Compute security_count and security_crc for next outgoing packet."""
    seed1 = (~seed1) & 0xFF
    seed1, seed2 = seed2, seed1        # XCHG
    seed3 ^= seed1
    count_byte = ((seed1 >> 4) ^ seed1) & 0xFF
    # count_byte → header byte 4 (security_count)
    # seed3 → header byte 5 (security_crc)
    return count_byte, seed3, seed1, seed2, seed3
```

The server validates these bytes to ensure packet integrity and ordering.

### Server Signature Exchange

When signature mode is enabled (security flag bit 4), the handshake includes a cryptographic signature exchange:

1. Server sends a signature blob in the `0x5000` packet data
2. Client reads and verifies the signature against local validation (session `+0x01B8`)
3. The signature data is compared using a dedicated comparison function (VA `0x004C4670`)
4. If valid, client stores the result and prepares a response signature
5. Response signature is encrypted with the session Blowfish and sent in `0x9000`

The signature exchange function at VA `0x004B2400` sets session state (`+0x0154`) to 1 and installs a callback pointer at `+0x022C`.

## Opcode Reference

> **Note**: The opcode names and descriptions in this section were derived from **client binary** (`sro_client.exe`) analysis. Many are inaccurate — the client uses internal dispatch IDs that don't match the actual packet semantics. For authoritative opcode names, packet structures, and field definitions, see:
> - [Server Binary Analysis](../../docs/server_binary_analysis.md) — 145+ opcodes with corrected names from `SR_GameServer_Andreas.exe` + xBot cross-reference
> - [Protocol Reference — Correction Table](protocol_reference.md#server-corrected-opcode-names) — 50+ opcode name corrections

### Opcode Groups

The dispatcher masks opcodes with `0xF800` (top 5 bits) to determine the message group, then uses group-specific jump tables or handler functions:

```asm
; At VA 0x007AFE20 — opcode group dispatch
movzx eax, word [eax]       ; read opcode
and   ax, 0xF800             ; mask to group
cmp   ax, 0x3000             ; entity/world group?
je    handle_entity_group
```

| Mask Result | Range | Group | Handler |
|-------------|-------|-------|---------|
| `0x2000` | `0x2000-0x27FF` | Login / Authentication | Login, version check |
| `0x3000` | `0x3000-0x37FF` | Entity / World | Spawn, despawn, movement |
| `0x3800` | `0x3800-0x3FFF` | Entity (extended) | Extended entity operations |
| `0x4000` | `0x4000-0x47FF` | Game actions | Combat, skills, items |
| `0x4800` | `0x4800-0x4FFF` | Game actions (ext) | Extended game actions |
| `0x5000` | `0x5000-0x57FF` | Handshake / System | Security handshake |
| `0x5800` | `0x5800-0x5FFF` | System (extended) | System messages |
| `0x9000` | `0x9000-0x97FF` | Handshake response | Client→server handshake |

### Known Opcodes — System & Handshake

| Opcode | Direction | Description | Evidence |
|--------|-----------|-------------|----------|
| `0x5000` | S→C | Handshake setup | `cmp ax, 0x5000` at VA `0x004B20DD`; `mov [ptr], 0x5000` at 3 locations |
| `0x9000` | C→S | Handshake response | `cmp ax, 0x9000` at VA `0x004B2229`; `mov [ptr], 0x9000` at 2 locations |
| `0xA106` | — | Agent server message | `cmp ax, 0xA106` |

### Known Opcodes — Client→Server (Send)

Found via `mov word ptr [buffer], opcode` instructions that write opcodes into outgoing packets:

| Opcode | Description | Evidence |
|--------|-------------|----------|
| `0x2001` | Login request | Written at VA `0x004CE8F8`; pushed at 4 locations |
| `0x2002` | Login (secondary) | Written at VA `0x004CF9DA` |
| `0x2026` | Version/patch check | Written at VA `0x00B9D6B6` |
| `0x6004` | Chat command | Written at VA `0x004D12E8` |
| `0x600D` | Chat message | Written at VA `0x004D624E`, `0x004D6355` |
| `0x6100` | Character action | Written at VA `0x004CEA98` |
| `0x6101` | Character action 2 | Written at VA `0x004C9439` |
| `0x6103` | Character action 3 | Written at VA `0x004CEB86` |
| `0x6104` | Character action 4 | Written at VA `0x004CF128` (3 locations) |
| `0x6106` | Character action 5 | Written at VA `0x004C94A9` |
| `0x6323` | Stall action | Written at VA `0x004C96B8` |
| `0xA004` | Agent action | Written at VA `0x004D0C98` |

### Known Opcodes — Server→Client (Receive)

> **Caution**: The descriptions below are client-internal handler labels, NOT the actual packet names. For example, what the client calls "Entity info" at `0x3011` is actually `SERVER_CHARACTER_DIED`; `0x3013` labeled "Entity data" is `SERVER_CHARACTER_DATA`. See [Server Binary Analysis §4-5](../../docs/server_binary_analysis.md#4-corrected-opcode-map-xbot--server-cross-reference) for the corrected map.

Found via paired `push opcode` patterns in handler functions (used for debug logging):

| Opcode | Description | Refs |
|--------|-------------|------|
| `0x3005` | World update | 1 |
| `0x3006` | World data | 1 |
| `0x3011` | Entity info | 1 |
| `0x3012` | Entity spawn | 2 |
| `0x3013` | Entity data | 1 |
| `0x3014` | Entity spawn (variant) | 2 |
| `0x3016` | Entity position update | 3 |
| `0x3019` | Entity state | 1 |
| `0x3020` | Entity despawn | 2 |
| `0x3021` | Entity action | 1 |
| `0x3022` | Entity action 2 | 1 |
| `0x3023` | Entity data update | 2 |
| `0x3053` | Group entity update | 6 |
| `0x306E` | Entity effect | 2 |
| `0x3080` | Movement update | 27 |
| `0x3091` | Movement state | 16 |
| `0x30C4` | Entity state change | 2 |
| `0x30D4` | Entity property | 2 |
| `0x3303` | Entity status | 2 |
| `0x347F` | Entity visual | 2 |
| `0x34A9` | Entity attribute | 2 |
| `0x34B6` | Entity flag | 2 |
| `0x34BF` | Entity parameter | 2 |
| `0x7001` | Game response | 4 |
| `0x7005` | Teleport | 2 |
| `0x7006` | Teleport response | 2 |
| `0x7007` | Resurrect/respawn | 17 |
| `0x7010` | Skill result | 70 |
| `0x7021` | Stall (player shop) | 2 |
| `0x7023` | Stall data | 2 |
| `0x7024` | Stall update | 2 |
| `0x7025` | Trade/exchange | 12 |
| `0x7031` | Entity visual update | 2 |
| `0x7034` | Buff/status effect | 66 |
| `0x703C` | Item update | 4 |
| `0x703E` | Equipment update | 4 |
| `0x703F` | Equipment state | 2 |
| `0x7045` | Item property | 2 |
| `0x7046` | Item action result | 19 |
| `0x704B` | Inventory update | 2 |
| `0x704C` | Inventory state | 6 |
| `0x704F` | Storage update | 2 |
| `0x7050` | Item visual | 2 |
| `0x7051` | Item data | 2 |
| `0x7059` | Experience update | 2 |
| `0x705A` | Level/stat update | 4 |
| `0x705B` | Character stat | 4 |
| `0x705D` | Gold/currency | 2 |
| `0x705E` | Character data | 8 |
| `0x7060`–`0x7063` | Character info | 2 each |
| `0x7069`–`0x706A` | Pet info/update | 2 each |
| `0x706B`–`0x706D` | Quest state/data/update | 2 each |
| `0x7074` | Party update | 32 |
| `0x7081`–`0x7084` | Guild base/data/info/update | 2 each |
| `0x70A1`–`0x70A2` | Union base/data | 2 each |
| `0x70A7` | Union update | 2 |
| `0x70B1`–`0x70B5` | Fortress base/data/info/update/state | 2 each |
| `0x70BA` | Fortress action | 2 |
| `0x70C0` | Arena state | 2 |
| `0x70C5` | NPC interaction | 18 |
| `0x70C6`–`0x70C7` | NPC data/dialog | 2 each |
| `0x70CB` | NPC response | 2 |
| `0x70D8`–`0x70D9` | Market data/update | 2 each |
| `0x70DB` | Market result | 2 |
| `0x70E1`–`0x70E6` | Alchemy result/data/update/state/info/complete | 2 each |
| `0x70EA` | Job data | 2 |
| `0x70F0`–`0x70F4` | Transport start/data/update/state/info | 2 each |
| `0x70F6` | Transport result | 2 |
| `0x70F9`–`0x70FD` | Transport end → Honor info | 2 each |
| `0x70FF` | Title data | 2 |
| `0x7103` | Academy data | 2 |
| `0x7105`–`0x7107` | Academy update/state/info | 2 each |
| `0x7110` | Premium state | 2 |
| `0x7112`–`0x7114` | Premium data/update/info | 2 each |
| `0x7116`–`0x7119` | System messages | 2-12 each |
| `0x711A` | System info | 12 |
| `0x7121` | Event data | 2 |
| `0x7150`–`0x7151` | PvP match/data | 6/6 |
| `0x7155` | PvP result | 8 |
| `0x7157`–`0x7158` | PvP state/update | 4/7 |
| `0x715F`–`0x7160` | PvP info/score | 2 each |
| `0x7168` | Battle result | 2 |
| `0x716A` | Battle data | 8 |
| `0x7202`–`0x7203` | Recall data/update | 2 each |
| `0x7250`–`0x7252` | Silk data/update/state | 2 each |
| `0x7256` | Cash shop | 2 |
| `0x7258`–`0x725A` | Cash shop data, item mall result, item visual change | 2 each |
| `0x7302`–`0x730D` | Ranking system (data, update, list, info, state, result, score, entry) | 2 each |
| `0x7402` | Calendar data | 2 |
| `0x7420` | Event state | 2 |
| `0x7450` | CTF/battle data | 6 |
| `0x7461`–`0x7478` | Arena system (match, data, update, score, state, info, result, ranking, end, reward, queue, start) | 2 each |
| `0x747A`–`0x747E` | Arena zone/achievement | 2 each |
| `0x7483` | Event reward | 2 |
| `0x74B2` | Collection data | 2 |
| `0x74D3`–`0x74E0` | Challenge system | 2-4 each |
| `0x7501` | Expansion data | 2 |
| `0x7506`–`0x750E` | Costume system | 2-6 each |
| `0x7515`–`0x751D` | Premium effects/buffs | 2 each |

### Dispatch Table Ranges

The client contains 17 switch-case jump tables that dispatch opcodes to handler functions. Each table covers a contiguous opcode range; the `sub eax, base` instruction indexes into the table:

| Range | Handlers | Jump Table VA | Category |
|-------|----------|---------------|----------|
| `0x180B`–`0x18B1` | 166 | `0x007BB438` | Object/Item actions |
| `0x1C07`–`0x1C7B` | 106 | `0x007BBAAC` | Inventory/Storage |
| `0x2008`–`0x200E` | 5 | `0x008777E8` | Character creation/selection |
| `0x2807`–`0x2876` | 99 | `0x007BBF58` | NPC/Shop/Exchange |
| `0x2C07`–`0x2C8C` | 105 | `0x007BB7DC` | Skill/Action |
| `0x3802`–`0x381E` | 28 | `0x007BB980` | Game config/settings |
| `0x3C0C`–`0x3C22` | 22 | `0x007BB998` | Chat system |
| `0x4407`–`0x4411` | 10 | `0x007BBA40` | Party/Union |
| `0x480F`–`0x481D` | 13 | `0x007BBED8` | Guild operations |
| `0x5006`–`0x5018` | 17 | `0x007BBEC8` | Stall/Market |
| `0x5407`–`0x5475` | 97 | `0x007BBD58` | Job/Transport/Alchemy |
| `0x5807`–`0x580F` | 8 | `0x007BBD20` | Academy/Mentor |
| `0x5B8C`–`0x5B8F` | 3 | `0x0084BE3C` | Honor/Title |
| `0x624B`–`0x624D` | 2 | `0x0084BF48` | Fortress |
| `0x6407`–`0x641F` | 20 | `0x007BBEB0` | Arena/PvP |
| `0x6809`–`0x6848` | 55 | `0x007BBE14` | Quest system |
| `0x7C07`–`0x7C2C` | 29 | `0x007BC080` | Item mall/Premium |

**Total: ~785 unique handler slots across 17 dispatch tables.**

Not every slot has a unique handler — some entries point to default/fallthrough handlers. The actual number of implemented opcodes is approximately 756 across these tables.

Additional opcodes outside dispatch tables (0x30XX–0x75XX range) are handled through virtual dispatch via vtable calls, adding ~160 more server→client opcodes.

**Estimated total unique opcodes: ~800+**

Additional message names from debug format strings:

| String | Context |
|--------|---------|
| `"SR_TELEPORT_ACK"` | Teleport acknowledgment (`"MSGID:0x%04X Wait My Char Data !!!"`) |
| `"SendNetMsgItemMall"` | Item mall purchase (`"ShopID(%d), Tab(%d), Index(%d)"`) |
| `"TELEPORTGATE -> Type(%d), Target(%d)"` | Teleport gate activation |
| `"Teleport Casting Cancel"` | Teleport cast interruption |
| `"Teleport Casting Start"` | Teleport cast begin |
| `"Restart Request : Type"` | Character respawn/restart |

## Message Dispatch

### CNetProcessIn Handlers

Inbound messages are dispatched through a multi-stage processing pipeline:

```
WSARecv completion (IOCP)
  → CPeerProcessIOCP / CPeerProcessOverlapped
    → CSession
      → Before handshake: _OnMsgReceivedBeforeHandshake()
          Accepts only 0x5000, responds with 0x9000
      → After handshake:
          → CNetProcessIn (main dispatcher)
            → Opcode group check (mask 0xF800)
            → sub eax, base → jmp [eax*4 + jump_table]
            → Per-opcode handler function
```

The main dispatcher uses two mechanisms:

1. **Jump table dispatch** (17 tables) for opcodes in ranges `0x180B`–`0x7C2C`. Each range uses `sub eax, base_opcode` followed by `jmp [eax*4 + table_addr]` to index directly into a function pointer table.

2. **Virtual dispatch** for opcodes in the `0x3000`–`0x35FF` entity range. The opcode group check (`and ax, 0xF800; cmp ax, 0x3000`) routes to a vtable call (`call [edx+0xAC]`), dispatching through the game object's virtual method table.

The cascading group dispatch at VA `0x008BB9E0` checks sequentially:
1. `0x3000` range → entity handlers (virtual dispatch)
2. `0x3800` range → extended entity handlers
3. `0x4000` range → game action handlers
4. `0x4800` range → extended game handlers
5. `0x5800` range → system handlers
6. Fall through to generic handler

Handler source files map to message categories:
- `NetProcessInInner.cpp` — Core game logic (chat, items, skills)
- `NetProcessInInterface.cpp` — UI state updates (over 2,100 `UIIT_*` action identifiers)
- `NetProcessInNavAndSkill.cpp` — Movement, navigation, skill execution
- `NetProcessInObject.cpp` — Entity state, equipment, buffs

**UIIT action identifiers**: The binary contains 2,118 unique `UIIT_*` (UI Item) wide-string identifiers that map network messages to UI actions. Examples:
- `UIIT_MSG_DEAL_ASKING` — Trade request received
- `UIIT_MSG_GUILD_ERR_INVALID` — Guild operation error
- `UIIT_STT_QUEST_GIVEUP_1` — Quest abandonment
- `UIIT_MSG_SKILL_EXECUTE` — Skill execution result

## Configuration Files

| File | Encoding | Purpose |
|------|----------|---------|
| `gateport.txt` | ASCII | Gateway server port number |
| `divisioninfo.txt` | ASCII | Server division list with IP addresses |
| `sv.t` | — | Server version data |
| `config\option.txt` | ASCII | Client settings |

The client version is checked against `SILKROADVERSION` and validated through `CPSVersionCheck` before connecting.

Network engine version is logged as: `"netengine(ver %0.2f)"`

Error if division info is missing: `"divisioninfo.txt open fail"`

### Keep-Alive

The client maintains keep-alive connections:
```
cannot establish keep alive session : %d.%d.%d.%d %d (bind %d.%d.%d.%d)
```

### UDP Ping

Latency measurement uses a separate UDP channel via `CUdpPingClient` / `CUdpPingBase`:
- REQ/ACK handshake protocol (`"REQ received!"`, `"ACK received!"`)
- Error handling: `"unreachable host!"`, `"recvfrom failed! [err: %d]"`

## Binary Analysis Reference

Key locations in `sro_client.exe` (PE32, image base `0x00400000`, sections: `.text` 9.9MB, `.rdata` 1.2MB, `.data` 237KB):

| Item | Virtual Address | Description |
|------|----------------|-------------|
| Handshake handler | `0x004B1DA0` | `_OnMsgReceivedBeforeHandshake()` function |
| Handshake response check | `0x004B22B0` | `0x9000` opcode validation |
| Blowfish P-array (static) | `0x00EE48B0` | Standard Blowfish init constants (starts `243F6A88 85A308D3`) |
| Blowfish SetKey | `0x004AA4C0` | Key expansion for session cipher |
| PRNG function (LFSR) | `0x004AFB80` | Security counter seed generation |
| Packet send encryption | `0x004B0D70` | Encrypts outbound packet data, adds security bytes |
| Security setup | `0x004B0CC0` | Initializes session security from handshake data |
| Signature exchange | `0x004B2400` | Server signature verification and response |
| Entity dispatch table | `0x00DD5CF0` | Jump table for entity message handlers (32+ entries) |
| Opcode group dispatch | `0x008BB9E0` | Cascading `0xF800` mask dispatch |
| Handshake debug strings | `0x00E1A710` | Format strings for handshake error logging |
| Network RTTI | `0x00AE6D34` | `CNetEngine` type info (start of network class RTTI) |
| "169841" (PK2 key) | `0x00E19450` | Base key string adjacent to `"media.pk2"` |
| "netengine(ver %0.2f)" | `0x00E1A098` | Engine version format string |
| MSG_ID format strings | `0x00DD5CE4` | Korean context + `"MSG_ID = %X"` |
| MsgStreamBuffer header | `0x009824A0` | `"MSGID:0x%X,R(%d),W(%d),T(%d)"` |
| `"GatewayServer"` | `0x00E1B310` | Server type identifier strings |

**Session object layout** (partial, reconstructed from field accesses):

| Offset | Size | Field |
|--------|------|-------|
| `+0x0008` | u32 | Session state/type |
| `+0x0158` | ~72B | CBlowFish instance (session encryption) |
| `+0x0164` | 8B | CRC key block |
| `+0x016C` | u8 | Security counter seed 1 |
| `+0x016D` | u8 | Security counter seed 2 |
| `+0x016E` | u8 | Security counter seed 3 |
| `+0x016F` | u8 | Security mode flags |
| `+0x01B8` | var | Server signature data |
| `+0x0200` | u8 | Session status flags |
| `+0x1034` | ptr | Message data buffer pointer |
| `+0x103C` | u16 | Message read cursor |
| `+0x103E` | u16 | Message write cursor |
| `+0x1048` | u32 | Has-data flag |
| `+0x1050` | ptr | Pointer to opcode field (u16) |
| `+0x1054` | ptr | Pointer to data size field (u16) |
| `+0x1058` | ptr | Pointer to security_count byte |
| `+0x105C` | ptr | Pointer to security_crc byte |
| `+0x1060` | u32 | Security byte counter index |

WS2_32.dll imports (39 functions): `WSASend`, `WSARecv`, `WSASocketA`, `WSAIoctl`, `WSACreateEvent`, `WSACloseEvent`, `WSAWaitForMultipleEvents`, `WSAResetEvent`, `WSASetEvent`, `WSASendTo`, `WSARecvFrom`, and standard socket functions.

## See Also

- [PK2 Format](pk2_format.md) — PK2 archive encryption (same CBlowFish, different key)
- [Asset File Formats](asset_formats.md) — Game asset format reference
- [Character & Equipment Rendering](character_rendering.md) — Character model assembly
- [Terrain & World Rendering](terrain_rendering.md) — Terrain geometry and shaders

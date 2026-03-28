# SERVER_ENTITY_GROUPSPAWN_END

> **Corrected name** (server RE): Was `SERVER_CHARACTER_SELECT_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3018` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008AC170` |
| Send site | `0x00533F42` (SR_GameServer.exe clean) |

### Fields

**No payload.** This is a marker packet sent after the bulk group-spawn data stream
(`0x3017` BEGIN → massive buffer → `0x3018` END). The server creates and immediately
sends this packet with no field writes between `SetMsg(0x3018)` and `SendMsg()`.

### Protocol Context

| Packet | Role |
|--------|------|
| `0x3017` `SERVER_ENTITY_GROUPSPAWN_BEGIN` | Opens the group-spawn sequence |
| `0x3019` `SERVER_ENTITY_GROUPSPAWN_DATA` | Bulk entity data (massive buffer) |
| `0x3018` `SERVER_ENTITY_GROUPSPAWN_END` | **Closes the sequence — no payload** |

### Binary Evidence

Decompiled (`r2ghidra`, `fcn.00533e70`):

```c
iVar1 = (**(*unaff_ESI + 0x278))(0x3018);  // CreatePacket(0x3018)
(**(*unaff_ESI + 0x27c))(iVar1);            // SendPacket — no field writes between
```

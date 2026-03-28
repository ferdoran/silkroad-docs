# SERVER_EXCHANGE_CANCELED

> **Corrected name** (server RE): Was `SERVER_INVENTORY_CLOSE` (client-derived). The server
> function and log strings confirm this is sent when a trade session is **cancelled**.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3088` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088BB50` |
| Send site | `0x004807B4` (SR_GameServer.exe clean) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `CancelReason` | `u16` | 2 | Reason code for cancellation |

### Structure Summary

```
  [0] CancelReason                       u16    // cancel/close reason code
```

Total payload: **2 bytes**

### Known Reason Codes

| Value | Constant | Description |
|-------|----------|-------------|
| `0x1811` | `SERVER_INTERNAL_ERROR` | Server-side error during trade |
| Other | TBD | Player-initiated cancel, timeout, etc. |

> The server log string `"Trading Session Closed Abnormally [reason: SERVER_INTERNAL_ERROR]"`
> maps to reason code `0x1811`.

### Protocol Context

| Packet | Payload |
|--------|---------|
| `0x3087` `SERVER_EXCHANGE_COMPLETED` | none |
| `0x3088` `SERVER_EXCHANGE_CANCELED` | **WORD reason** |

### Binary Evidence

Disassembly at VA `0x4807B4` (SR_GameServer.exe clean):

```asm
004807B4: push 0x3088           ; opcode
004807B9: call eax              ; CreatePacket(0x3088)
004807BB: mov  edi, eax         ; packet handle
004807BD: lea  ecx, [ebp+0x10]  ; &arg_10h (reason code)
004807C0: push ecx
004807C1: mov  eax, 2           ; size = 2 bytes (WORD)
004807C6: mov  ecx, edi
004807C8: call 0x404090         ; WriteField(reason, 2 bytes)
004807D0: mov  eax, [edx+0x27c] ; SendPacket vtable slot
004807D8: call eax              ; SendPacket
```

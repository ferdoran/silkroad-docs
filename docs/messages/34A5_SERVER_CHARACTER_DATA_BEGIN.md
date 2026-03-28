# SERVER_CHARACTER_DATA_BEGIN

> **Corrected name** (server RE): Was `SERVER_EVENT_RESPONSE` (client-derived).
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34A5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x008A6580` |
| Send site | `0x004E3E5D` (SR_GameServer.exe clean) |
| Multi-part | Envelope: `0x34A5` BEGIN / massive buffer (`0x3013`) / `0x34A6` END |

### Fields

**No payload.** This is a marker sent immediately before the character data buffer
(`0x3013 SERVER_CHARACTER_DATA`) to signal the start of the multi-part character
data transfer.

### Protocol Context

| Packet | Role |
|--------|------|
| `0x34A5` `SERVER_CHARACTER_DATA_BEGIN` | **Start marker — no payload** |
| `0x3013` `SERVER_CHARACTER_DATA` | Full character data (massive buffer) |
| `0x34A6` `SERVER_CHARACTER_DATA_END` | End marker — no payload |

### Binary Evidence

Decompiled (`r2ghidra`, `fcn.004e3bb0`):

```c
// After building the full character data buffer at 0xc66a00:
uVar2 = (**(iVar1 + 0x278))(0x34a5);    // CreatePacket(0x34A5)
(**(iVar1 + 0x27c))(uVar2);              // SendPacket — no field writes
fcn.00430a20(0xc66a00);                  // Send character data buffer as 0x3013
uVar2 = (**(iVar1 + 0x278))(0x34a6);    // CreatePacket(0x34A6)
(**(iVar1 + 0x27c))(uVar2);              // SendPacket — no field writes
```

# SERVER_GLOBAL_EVENT

| Property | Value |
|----------|-------|
| Opcode | `0x3405` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0086D550` |
| Send site | `0x004F0A6C` (SR_GameServer.exe clean) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `EventType` | `u8` | 1 | Global event category |
| 2 | `EventData` | `u32` | 4 | Event-specific data (timer, ID, etc.) |

### Structure Summary

```
  [0] EventType                          u8     // event category
  [1] EventData                          u32    // event payload
```

Total payload: **5 bytes**

### EventType Values

| Value | Description |
|-------|-------------|
| `0` → `uStack_1c = 4` | Event type 0 (maps to internal constant 4) |
| `1` → `uStack_1c = 3` | Event type 1 (maps to internal constant 3) |
| Other | Triggers abort (`fcn.00964b60`) — unsupported |

### Binary Evidence

Decompiled (`r2ghidra`, `fcn.004f0a00`):

```c
uVar3 = (**(*unaff_EDI + 0x278))(0x3405);   // CreatePacket(0x3405)
fcn.00404090(&arg_8h);                        // Write EventType (1 byte, eax=1)
uVar4 = fcn.004f8860();                       // Compute/retrieve EventData
fcn.00404090(uVar4);                          // Write EventData (4 bytes, eax=4)
(**(*unaff_EDI + 0x27c))(uVar3);             // SendPacket
```

Disassembly write sizes confirmed: VA `0x4F0A82` `eax=1` (BYTE), VA `0x4F0A9C` `eax=4` (DWORD).

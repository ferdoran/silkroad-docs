# CLIENT_ENTITY_POSITION_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB070` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A52F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A52FF` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A530D` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwTargetUID                    u32
```

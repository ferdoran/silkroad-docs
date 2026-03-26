# CLIENT_MOVEMENT_CANCEL

| Property | Value |
|----------|-------|
| Opcode | `0xB031` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D8C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088D8CE` |
| 2 | `wParam` | `u16` | 2 | `0x0088D8E8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] wParam                         u16
```

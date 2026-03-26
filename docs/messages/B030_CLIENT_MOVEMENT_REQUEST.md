# CLIENT_MOVEMENT_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB030` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D840` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwDestID` | `u32` | 4 | `0x0088D861` |
| 2 | `dwParam1` | `u32` | 4 | `0x0088D86F` |
| 3 | `dwParam2` | `u32` | 4 | `0x0088D87D` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwDestID                       u32
  [   4] dwParam1                       u32
  [   8] dwParam2                       u32
```

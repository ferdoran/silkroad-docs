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
| 1 | `dwUniqueID` | `u32` | 4 | `0x0088D861` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088D86F` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088D87D` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

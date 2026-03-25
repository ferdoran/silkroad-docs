# CLIENT_UNIQUE_ID

| Property | Value |
|----------|-------|
| Opcode | `0xB04F` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A50E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x008A50F1` |
| 2 | `bytesData_1` | `bytes[14]` | 14 | `0x008A50FF` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A510D` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] wParam                         u16
  [   2] bytesData_1                    bytes[14]
  [  16] dwField_03                     u32
```

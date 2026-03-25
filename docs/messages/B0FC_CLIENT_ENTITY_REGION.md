# CLIENT_ENTITY_REGION

| Property | Value |
|----------|-------|
| Opcode | `0xB0FC` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087FD00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0099A85F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0099A86F` |
| 3 | `dwField_03` | `u32` | 4 | `0x0099A87D` |
| 4 | `byField_04` | `u8` | 1 | `0x0099A88B` |
| 5 | `dwField_05` | `u32` | 4 | `0x0099A8EB` |
| 6 | `wField_06` | `u16` | 2 | `0x0099A8F9` |
| 7 | `bytesData_6` | `bytes` | variable | `0x0099A93A` |
| 8 | `byField_08` | `u8` | 1 | `0x0099A948` |
| 9 | `wField_09` | `u16` | 2 | `0x0099A956` |
| 10 | `bytesData_9` | `bytes` | variable | `0x0099A994` |
| 11 | `dwField_11` | `u32` | 4 | `0x0099A9A2` |
| 12 | `byField_12` | `u8` | 1 | `0x0099A9B0` |

**Minimum size**: 27 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
  [  13] dwField_05                     u32
  [  17] wField_06                      u16
  [  19] bytesData_6                    bytes  (variable length)
  [   0] byField_08                     u8
  [   1] wField_09                      u16
  [   3] bytesData_9                    bytes  (variable length)
  [   0] dwField_11                     u32
  [   4] byField_12                     u8
```

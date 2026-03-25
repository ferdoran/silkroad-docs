# CLIENT_STALL_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0D8` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008812B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008812E3` |
| 2 | `dwField_02` | `u32` | 4 | `0x008812F1` |
| 3 | `byField_03` | `u8` | 1 | `0x008B94E5` |
| 4 | `byField_04` | `u8` | 1 | `0x008B94F2` |
| 5 | `byField_05` | `u8` | 1 | `0x008B94FF` |
| 6 | `dwField_06` | `u32` | 4 | `0x008B9511` |
| 7 | `byField_07` | `u8` | 1 | `0x008B954E` |
| 8 | `byField_08` | `u8` | 1 | `0x008B9560` |
| 9 | `byField_09` | `u8` | 1 | `0x008B9579` |
| 10 | `byField_10` | `u8` | 1 | `0x008B6F3D` |
| 11 | `byField_11` | `u8` | 1 | `0x008B6F56` |
| 12 | `dwField_12` | `u32` | 4 | `0x008B6FFF` |
| 13 | `byField_13` | `u8` | 1 | `0x008B95EA` |
| 14 | `dwField_14` | `u32` | 4 | `0x008B9609` |

**Total size**: 26 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] byField_03                     u8
  [   6] byField_04                     u8
  [   7] byField_05                     u8
  [   8] dwField_06                     u32
  [  12] byField_07                     u8
  [  13] byField_08                     u8
  [  14] byField_09                     u8
  [  15] byField_10                     u8
  [  16] byField_11                     u8
  [  17] dwField_12                     u32
  [  21] byField_13                     u8
  [  22] dwField_14                     u32
```

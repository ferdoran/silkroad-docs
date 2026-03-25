# CLIENT_STALL_BUY

| Property | Value |
|----------|-------|
| Opcode | `0xB471` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008986C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0099AD49` |
| 2 | `bytesData_1` | `bytes[16]` | 16 | `0x0099AD57` |
| 3 | `byField_03` | `u8` | 1 | `0x0099AD65` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byField_06` | `u8` | 1 | `0x009995DF` |
| 7 | `dwField_07` | `u32` | 4 | `0x00999621` |
| 8 | `dwField_08` | `u32` | 4 | `0x0099962F` |
| 9 | `dwField_09` | `u32` | 4 | `0x0099963D` |
| 10 | `wField_10` | `u16` | 2 | `0x0099964B` |
| 11 | `bytesData_10` | `bytes` | variable | `0x009996A4` |
| 12 | `byField_12` | `u8` | 1 | `0x009996B2` |
| 13 | `byField_13` | `u8` | 1 | `0x009996C0` |
| 14 | `bytesData_13` | `bytes` | variable | `0x009996CD` |
| 15 | `byField_15` | `u8` | 1 | `0x009996DB` |
| 16 | `byField_16` | `u8` | 1 | `0x009996E9` |
| 17 | `dwField_17` | `u32` | 4 | `0x009996F7` |
| 18 | `byField_18` | `u8` | 1 | `0x00999705` |
| 19 | `dwField_19` | `u32` | 4 | `0x00999713` |
| 20 | `wField_20` | `u16` | 2 | `0x00999721` |
| 21 | `wField_21` | `u16` | 2 | `0x0099972F` |
| 22 | `wField_22` | `u16` | 2 | `0x0099973D` |
| 23 | `wField_23` | `u16` | 2 | `0x0099974B` |
| 24 | `wField_24` | `u16` | 2 | `0x00999759` |
| 25 | `bytesData_24` | `bytes` | variable | `0x009997AD` |

**Minimum size**: 61 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] bytesData_1                    bytes[16]
  [  20] byField_03                     u8
  [  21] wField_04                      u16
  [  23] bytesData_4                    bytes  (variable length)
  [   0] byField_06                     u8
  [   1] dwField_07                     u32
  [   5] dwField_08                     u32
  [   9] dwField_09                     u32
  [  13] wField_10                      u16
  [  15] bytesData_10                   bytes  (variable length)
  [   0] byField_12                     u8
  [   1] byField_13                     u8
  [   2] bytesData_13                   bytes  (variable length)
  [   0] byField_15                     u8
  [   1] byField_16                     u8
  [   2] dwField_17                     u32
  [   6] byField_18                     u8
  [   7] dwField_19                     u32
  [  11] wField_20                      u16
  [  13] wField_21                      u16
  [  15] wField_22                      u16
  [  17] wField_23                      u16
  [  19] wField_24                      u16
  [  21] bytesData_24                   bytes  (variable length)
```

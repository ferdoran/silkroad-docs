# SERVER_STALL_UPDATE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x3C81` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x00899630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089963E` |
| 2 | `dwField_02` | `u32` | 4 | `0x0099AD49` |
| 3 | `bytesData_2` | `bytes[16]` | 16 | `0x0099AD57` |
| 4 | `byField_04` | `u8` | 1 | `0x0099AD65` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x009995DF` |
| 8 | `dwField_08` | `u32` | 4 | `0x00999621` |
| 9 | `dwField_09` | `u32` | 4 | `0x0099962F` |
| 10 | `dwField_10` | `u32` | 4 | `0x0099963D` |
| 11 | `wField_11` | `u16` | 2 | `0x0099964B` |
| 12 | `bytesData_11` | `bytes` | variable | `0x009996A4` |
| 13 | `byField_13` | `u8` | 1 | `0x009996B2` |
| 14 | `byField_14` | `u8` | 1 | `0x009996C0` |
| 15 | `bytesData_14` | `bytes` | variable | `0x009996CD` |
| 16 | `byField_16` | `u8` | 1 | `0x009996DB` |
| 17 | `byField_17` | `u8` | 1 | `0x009996E9` |
| 18 | `dwField_18` | `u32` | 4 | `0x009996F7` |
| 19 | `byField_19` | `u8` | 1 | `0x00999705` |
| 20 | `dwField_20` | `u32` | 4 | `0x00999713` |
| 21 | `wField_21` | `u16` | 2 | `0x00999721` |
| 22 | `wField_22` | `u16` | 2 | `0x0099972F` |
| 23 | `wField_23` | `u16` | 2 | `0x0099973D` |
| 24 | `wField_24` | `u16` | 2 | `0x0099974B` |
| 25 | `wField_25` | `u16` | 2 | `0x00999759` |
| 26 | `bytesData_25` | `bytes` | variable | `0x009997AD` |

**Minimum size**: 62 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] bytesData_2                    bytes[16]
  [  21] byField_04                     u8
  [  22] wField_05                      u16
  [  24] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] dwField_09                     u32
  [   9] dwField_10                     u32
  [  13] wField_11                      u16
  [  15] bytesData_11                   bytes  (variable length)
  [   0] byField_13                     u8
  [   1] byField_14                     u8
  [   2] bytesData_14                   bytes  (variable length)
  [   0] byField_16                     u8
  [   1] byField_17                     u8
  [   2] dwField_18                     u32
  [   6] byField_19                     u8
  [   7] dwField_20                     u32
  [  11] wField_21                      u16
  [  13] wField_22                      u16
  [  15] wField_23                      u16
  [  17] wField_24                      u16
  [  19] wField_25                      u16
  [  21] bytesData_25                   bytes  (variable length)
```

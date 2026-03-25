# CLIENT_SIEGE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB05D` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00895BB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00895BFB` |
| 2 | `byField_02` | `u8` | 1 | `0x00895C25` |
| 3 | `dwField_03` | `u32` | 4 | `0x00895CCE` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `dwField_06` | `u32` | 4 | `0x00895CEE` |
| 7 | `dwField_07` | `u32` | 4 | `0x00895D1D` |
| 8 | `dwField_08` | `u32` | 4 | `0x00895D2E` |
| 9 | `dwField_09` | `u32` | 4 | `0x00895D3F` |
| 10 | `byField_10` | `u8` | 1 | `0x00895D4D` |
| 11 | `dwField_11` | `u32` | 4 | `0x00895D8B` |
| 12 | `byField_12` | `u8` | 1 | `0x00895D99` |
| 13 | `dwField_13` | `u32` | 4 | `0x00895DAE` |
| 14 | `byField_14` | `u8` | 1 | `0x00895EA3` |
| 15 | `dwField_15` | `u32` | 4 | `0x00895EC2` |

**Minimum size**: 39 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] wField_04                      u16
  [   8] bytesData_4                    bytes  (variable length)
  [   0] dwField_06                     u32
  [   4] dwField_07                     u32
  [   8] dwField_08                     u32
  [  12] dwField_09                     u32
  [  16] byField_10                     u8
  [  17] dwField_11                     u32
  [  21] byField_12                     u8
  [  22] dwField_13                     u32
  [  26] byField_14                     u8
  [  27] dwField_15                     u32
```

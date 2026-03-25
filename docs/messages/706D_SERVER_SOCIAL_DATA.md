# SERVER_SOCIAL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x706D` |
| Direction | Server → Client |
| Group | Chat/Social |
| Handler(s) | `0x008841F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088423B` |
| 2 | `byField_02` | `u8` | 1 | `0x00884255` |
| 3 | `byField_03` | `u8` | 1 | `0x00884263` |
| 4 | `byField_04` | `u8` | 1 | `0x00884271` |
| 5 | `dwField_05` | `u32` | 4 | `0x00884392` |
| 6 | `dwField_06` | `u32` | 4 | `0x008843A0` |
| 7 | `wField_07` | `u16` | 2 | `0x004F7A7D` |
| 8 | `bytesData_7` | `bytes` | variable | `0x004F7AB9` |
| 9 | `byField_09` | `u8` | 1 | `0x008843BF` |
| 10 | `byField_10` | `u8` | 1 | `0x008843CD` |
| 11 | `byField_11` | `u8` | 1 | `0x008843DB` |
| 12 | `byField_12` | `u8` | 1 | `0x008843E9` |
| 13 | `byField_13` | `u8` | 1 | `0x008843F7` |
| 14 | `byField_14` | `u8` | 1 | `0x00884405` |
| 15 | `wField_15` | `u16` | 2 | `0x0088460D` |

**Minimum size**: 22 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] wField_07                      u16
  [  14] bytesData_7                    bytes  (variable length)
  [   0] byField_09                     u8
  [   1] byField_10                     u8
  [   2] byField_11                     u8
  [   3] byField_12                     u8
  [   4] byField_13                     u8
  [   5] byField_14                     u8
  [   6] wField_15                      u16
```

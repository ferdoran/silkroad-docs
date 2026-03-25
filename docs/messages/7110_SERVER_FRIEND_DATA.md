# SERVER_FRIEND_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x7110` |
| Direction | Server → Client |
| Group | Chat Extended |
| Handler(s) | `0x0087FD90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0099AB67` |
| 2 | `dwField_02` | `u32` | 4 | `0x0087FF1D` |
| 3 | `dwField_03` | `u32` | 4 | `0x0087FF2F` |
| 4 | `byField_04` | `u8` | 1 | `0x0087FF3C` |
| 5 | `dwField_05` | `u32` | 4 | `0x0087FF49` |
| 6 | `dwField_06` | `u32` | 4 | `0x0087FF56` |
| 7 | `dwField_07` | `u32` | 4 | `0x0087FF63` |
| 8 | `dwField_08` | `u32` | 4 | `0x0087FF70` |
| 9 | `dwField_09` | `u32` | 4 | `0x0087FF7D` |
| 10 | `wField_10` | `u16` | 2 | `0x004F7A7D` |
| 11 | `bytesData_10` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 32 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] dwField_05                     u32
  [  14] dwField_06                     u32
  [  18] dwField_07                     u32
  [  22] dwField_08                     u32
  [  26] dwField_09                     u32
  [  30] wField_10                      u16
  [  32] bytesData_10                   bytes  (variable length)
```

# CLIENT_RANKING_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB47B` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008907F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089082C` |
| 2 | `dwField_02` | `u32` | 4 | `0x00890857` |
| 3 | `dwField_03` | `u32` | 4 | `0x00890865` |
| 4 | `byField_04` | `u8` | 1 | `0x00890873` |
| 5 | `wField_05` | `u16` | 2 | `0x0087356D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x008735A9` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089088D` |
| 8 | `wField_08` | `u16` | 2 | `0x00890913` |

**Minimum size**: 18 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] wField_05                      u16
  [  12] bytesData_5                    bytes  (variable length)
  [   0] dwField_07                     u32
  [   4] wField_08                      u16
```

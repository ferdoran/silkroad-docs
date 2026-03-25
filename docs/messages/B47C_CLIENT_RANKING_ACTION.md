# CLIENT_RANKING_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB47C` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x00890960` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089099C` |
| 2 | `dwField_02` | `u32` | 4 | `0x008909C7` |
| 3 | `dwField_03` | `u32` | 4 | `0x008909D5` |
| 4 | `byField_04` | `u8` | 1 | `0x008909E3` |
| 5 | `wField_05` | `u16` | 2 | `0x0087356D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x008735A9` |
| 7 | `wField_07` | `u16` | 2 | `0x00890A66` |

**Minimum size**: 14 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] wField_05                      u16
  [  12] bytesData_5                    bytes  (variable length)
  [   0] wField_07                      u16
```

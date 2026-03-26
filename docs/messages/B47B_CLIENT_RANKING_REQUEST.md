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
| 2 | `dwRankingID` | `u32` | 4 | `0x00890857` |
| 3 | `dwParam1` | `u32` | 4 | `0x00890865` |
| 4 | `byCategory` | `u8` | 1 | `0x00890873` |
| 5 | `dwFilterID` | `u16` | 2 | `0x0087356D` |
| 6 | `wPage` | `bytes` | variable | `0x008735A9` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089088D` |
| 8 | `wField_08` | `u16` | 2 | `0x00890913` |

**Minimum size**: 18 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_ENTRY` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwRankingID                    u32
  [   5] dwParam1                       u32
  [   9] byCategory                     u8
  [  10] dwFilterID                     u16
  [  12] wPage                          bytes  (variable length)
  [   0] dwField_07                     u32
  [   4] wField_08                      u16
```

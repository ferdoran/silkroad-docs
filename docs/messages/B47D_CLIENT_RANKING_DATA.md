# CLIENT_RANKING_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB47D` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DF80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DF8E` |
| 2 | `dwParam` | `u32` | 4 | `0x0088DFA9` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_PULL_DELETE` | UI |
| `UIIT_STT_TC_MACHING_DELETE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam                        u32
  [   5] bytesData_2                    bytes  (variable length)
```

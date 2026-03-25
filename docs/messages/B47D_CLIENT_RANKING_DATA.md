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
| 2 | `dwField_02` | `u32` | 4 | `0x0088DFA9` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] bytesData_2                    bytes  (variable length)
```

# SERVER_ACADEMY_LIST

| Property | Value |
|----------|-------|
| Opcode | `0x3257` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008905D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00890668` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
```

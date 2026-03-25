# SERVER_ENTITY_UPDATE_GUILD

| Property | Value |
|----------|-------|
| Opcode | `0x3120` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088D700` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D70F` |
| 2 | `wValue` | `u16` | 2 | `0x0088D71D` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wValue                         u16
```

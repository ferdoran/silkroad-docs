# SERVER_COS_REMOVE

| Property | Value |
|----------|-------|
| Opcode | `0x315C` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008993B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008993D1` |
| 2 | `dwField_02` | `u32` | 4 | `0x008993DF` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
```

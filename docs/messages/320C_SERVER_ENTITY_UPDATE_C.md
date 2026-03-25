# SERVER_ENTITY_UPDATE_C

| Property | Value |
|----------|-------|
| Opcode | `0x320C` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088F880` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0088F8C8` |
| 2 | `wField_02` | `u16` | 2 | `0x0088F8D6` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
```

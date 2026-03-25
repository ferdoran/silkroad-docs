# SERVER_ENTITY_STATE_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x3206` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008A4990` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00A56731` |
| 2 | `dwField_02` | `u32` | 4 | `0x00A5673F` |
| 3 | `wField_03` | `u16` | 2 | `0x00A5674D` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] wField_03                      u16
```

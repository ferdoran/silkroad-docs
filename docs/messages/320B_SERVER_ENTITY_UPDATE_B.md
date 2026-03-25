# SERVER_ENTITY_UPDATE_B

| Property | Value |
|----------|-------|
| Opcode | `0x320B` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00898FF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899019` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899027` |
| 3 | `dwField_03` | `u32` | 4 | `0x00899035` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

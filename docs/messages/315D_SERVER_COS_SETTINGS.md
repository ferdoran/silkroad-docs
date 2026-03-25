# SERVER_COS_SETTINGS

| Property | Value |
|----------|-------|
| Opcode | `0x315D` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00899480` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089949B` |
| 2 | `dwField_02` | `u32` | 4 | `0x008994A9` |
| 3 | `dwField_03` | `u32` | 4 | `0x008994B7` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

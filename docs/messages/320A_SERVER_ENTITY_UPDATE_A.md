# SERVER_ENTITY_UPDATE_A

| Property | Value |
|----------|-------|
| Opcode | `0x320A` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00898F80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00898FA9` |
| 2 | `dwField_02` | `u32` | 4 | `0x00898FB7` |
| 3 | `dwField_03` | `u32` | 4 | `0x00898FC5` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

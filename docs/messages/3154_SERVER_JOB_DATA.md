# SERVER_JOB_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x3154` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00882DE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00882DFF` |
| 2 | `dwField_02` | `u32` | 4 | `0x00882E0D` |
| 3 | `dwField_03` | `u32` | 4 | `0x00882E1B` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

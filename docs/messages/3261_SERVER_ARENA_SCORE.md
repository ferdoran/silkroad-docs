# SERVER_ARENA_SCORE

| Property | Value |
|----------|-------|
| Opcode | `0x3261` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0089A0D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089A0F1` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089A103` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089A111` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089A11F` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089A12D` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] dwField_05                     u32
```

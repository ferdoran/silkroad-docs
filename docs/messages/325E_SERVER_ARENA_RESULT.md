# SERVER_ARENA_RESULT

| Property | Value |
|----------|-------|
| Opcode | `0x325E` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00899E60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899E87` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899E95` |
| 3 | `dwField_03` | `u32` | 4 | `0x00899EA3` |
| 4 | `byField_04` | `u8` | 1 | `0x00899EB1` |

**Total size**: 13 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
```

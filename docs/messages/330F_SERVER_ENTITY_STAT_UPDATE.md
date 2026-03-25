# SERVER_ENTITY_STAT_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x330F` |
| Direction | Server → Client |
| Group | Game Extended 3 |
| Handler(s) | `0x008A59E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A5A31` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A5A3F` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A5A4D` |
| 4 | `byField_04` | `u8` | 1 | `0x008A5A74` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A5AA9` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A5AC3` |

**Total size**: 21 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
  [  13] dwField_05                     u32
  [  17] dwField_06                     u32
```

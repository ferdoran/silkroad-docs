# SERVER_COS_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x315B` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00899350` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899373` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899381` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089938F` |
| 4 | `byField_04` | `u8` | 1 | `0x0089939D` |

**Total size**: 13 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
```

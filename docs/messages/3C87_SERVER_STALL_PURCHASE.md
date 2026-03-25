# SERVER_STALL_PURCHASE

| Property | Value |
|----------|-------|
| Opcode | `0x3C87` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089B7B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089B80A` |
| 2 | `byField_02` | `u8` | 1 | `0x0089B834` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089B855` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089B863` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089B871` |
| 6 | `byField_06` | `u8` | 1 | `0x0089B92E` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089B94B` |
| 8 | `dwField_08` | `u32` | 4 | `0x0089B959` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089B967` |
| 10 | `byField_10` | `u8` | 1 | `0x0089B9F8` |
| 11 | `dwField_11` | `u32` | 4 | `0x0089BA11` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089BA1F` |
| 13 | `dwField_13` | `u32` | 4 | `0x0089BA2D` |

**Total size**: 40 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] dwField_04                     u32
  [  10] dwField_05                     u32
  [  14] byField_06                     u8
  [  15] dwField_07                     u32
  [  19] dwField_08                     u32
  [  23] dwField_09                     u32
  [  27] byField_10                     u8
  [  28] dwField_11                     u32
  [  32] dwField_12                     u32
  [  36] dwField_13                     u32
```

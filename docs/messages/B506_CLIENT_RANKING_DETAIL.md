# CLIENT_RANKING_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB506` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x008A3470` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A34BB` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A350B` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A3519` |
| 4 | `byField_04` | `u8` | 1 | `0x008A3527` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A3535` |

**Total size**: 14 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] dwField_05                     u32
```

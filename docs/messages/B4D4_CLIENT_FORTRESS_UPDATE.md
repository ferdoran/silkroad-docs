# CLIENT_FORTRESS_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB4D4` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x0088E090` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088E0A3` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088E0BC` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088E0CA` |
| 4 | `byField_04` | `u8` | 1 | `0x0088E129` |
| 5 | `dwField_05` | `u32` | 4 | `0x0088E149` |
| 6 | `dwField_06` | `u32` | 4 | `0x0088E157` |

**Total size**: 18 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] dwField_05                     u32
  [  14] dwField_06                     u32
```

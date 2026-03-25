# CLIENT_ARENA_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB160` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x0089B660` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089B692` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089B6A8` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089B6B6` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
```

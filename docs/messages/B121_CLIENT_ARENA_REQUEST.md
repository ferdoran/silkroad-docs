# CLIENT_ARENA_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB121` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x0089F710` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0089F72F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089F73D` |
| 3 | `byField_03` | `u8` | 1 | `0x0089F74B` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] byField_03                     u8
```

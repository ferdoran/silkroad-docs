# CLIENT_SKILL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB202` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x00880E90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880E9F` |
| 2 | `dwField_02` | `u32` | 4 | `0x00880EB9` |
| 3 | `byField_03` | `u8` | 1 | `0x00880EC7` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] byField_03                     u8
```

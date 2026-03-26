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
| 1 | `byFlag1` | `u8` | 1 | `0x0088E0A3` |
| 2 | `dwUniqueID1` | `u32` | 4 | `0x0088E0BC` |
| 3 | `dwParam1` | `u32` | 4 | `0x0088E0CA` |
| 4 | `byFlag2` | `u8` | 1 | `0x0088E129` |
| 5 | `dwUniqueID2` | `u32` | 4 | `0x0088E149` |
| 6 | `dwParam2` | `u32` | 4 | `0x0088E157` |

**Total size**: 18 bytes

### Structure Summary

```
  [   0] byFlag1                        u8
  [   1] dwUniqueID1                    u32
  [   5] dwParam1                       u32
  [   9] byFlag2                        u8
  [  10] dwUniqueID2                    u32
  [  14] dwParam2                       u32
```

# CLIENT_GUILD_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB30D` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x008A1360` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A1378` |
| 2 | `wCategoryID` | `u16` | 2 | `0x008A1392` |
| 3 | `byHasItems` | `u8` | 1 | `0x008A13A0` |
| 4 | `dwPageID` | `u32` | 4 | `0x008A13C3` |
| 5 | `wItemCount` | `u16` | 2 | `0x008A13D1` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wCategoryID                    u16
  [   3] byHasItems                     u8
  [   4] dwPageID                       u32
  [   8] wItemCount                     u16
```

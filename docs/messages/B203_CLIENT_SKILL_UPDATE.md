# CLIENT_SKILL_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB203` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x00880CC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880CCF` |
| 2 | `dwMasteryID` | `u32` | 4 | `0x00880CE9` |
| 3 | `byAction` | `u8` | 1 | `0x00880CF7` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwMasteryID                    u32
  [   5] byAction                       u8
```

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
| 1 | `dwTradeID` | `u32` | 4 | `0x0089F72F` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x0089F73D` |
| 3 | `byFlags` | `u8` | 1 | `0x0089F74B` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] dwTradeID                      u32
  [   4] dwTargetUID                    u32
  [   8] byFlags                        u8
```

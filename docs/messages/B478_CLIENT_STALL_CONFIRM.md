# CLIENT_STALL_CONFIRM

| Property | Value |
|----------|-------|
| Opcode | `0xB478` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x00899940` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0089994E` |
| 2 | `wParam` | `u16` | 2 | `0x00899987` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

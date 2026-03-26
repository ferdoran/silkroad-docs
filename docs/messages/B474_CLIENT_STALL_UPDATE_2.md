# CLIENT_STALL_UPDATE_2

| Property | Value |
|----------|-------|
| Opcode | `0xB474` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x00899800` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0089980E` |
| 2 | `wParam` | `u16` | 2 | `0x00899828` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

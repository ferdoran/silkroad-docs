# CLIENT_STALL_BROWSE

| Property | Value |
|----------|-------|
| Opcode | `0xB470` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008995E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008995EE` |
| 2 | `wParam` | `u16` | 2 | `0x00899608` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

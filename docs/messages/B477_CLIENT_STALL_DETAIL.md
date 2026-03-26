# CLIENT_STALL_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB477` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008998F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008998FE` |
| 2 | `wParam` | `u16` | 2 | `0x00899918` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

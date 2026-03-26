# CLIENT_STALL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB476` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008998A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008998AE` |
| 2 | `wParam` | `u16` | 2 | `0x008998C8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

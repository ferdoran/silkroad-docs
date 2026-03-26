# CLIENT_JOB_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB105` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00881CB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881CBE` |
| 2 | `wParam` | `u16` | 2 | `0x00881CD8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

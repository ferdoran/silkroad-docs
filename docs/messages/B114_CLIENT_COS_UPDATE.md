# CLIENT_COS_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB114` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00881F30` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881F3E` |
| 2 | `wParam` | `u16` | 2 | `0x00881F58` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

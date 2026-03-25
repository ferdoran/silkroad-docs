# CLIENT_STALL_CLOSE

| Property | Value |
|----------|-------|
| Opcode | `0xB473` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x008997A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008997AE` |
| 2 | `wField_02` | `u16` | 2 | `0x008997D5` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

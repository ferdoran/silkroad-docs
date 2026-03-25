# CLIENT_STALL_INFO

| Property | Value |
|----------|-------|
| Opcode | `0xB475` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x00899850` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089985E` |
| 2 | `wField_02` | `u16` | 2 | `0x00899878` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

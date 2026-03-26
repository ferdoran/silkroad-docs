# CLIENT_ARENA_STATUS

| Property | Value |
|----------|-------|
| Opcode | `0xB25A` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x0088D9C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D9CE` |
| 2 | `byStatus` | `u8` | 1 | `0x0088D9E4` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byStatus                       u8
```

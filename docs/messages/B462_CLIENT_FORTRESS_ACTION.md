# CLIENT_FORTRESS_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB462` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DEC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DECE` |
| 2 | `wLevel` | `u16` | 2 | `0x0088DF0D` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wLevel                         u16
```

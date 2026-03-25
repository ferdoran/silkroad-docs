# CLIENT_FORTRESS_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB461` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x0088D910` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D91E` |
| 2 | `wField_02` | `u16` | 2 | `0x0088D987` |
| 3 | `byField_03` | `u8` | 1 | `0x0088D9CE` |
| 4 | `byField_04` | `u8` | 1 | `0x0088D9E4` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] byField_03                     u8
  [   4] byField_04                     u8
```

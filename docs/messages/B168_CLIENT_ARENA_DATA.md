# CLIENT_ARENA_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB168` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x0089C3A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089C41E` |
| 2 | `byField_02` | `u8` | 1 | `0x0089C42C` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 4 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
```

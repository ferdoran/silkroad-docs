# CLIENT_GUILD_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB309` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x00886170` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008861AD` |
| 2 | `byField_02` | `u8` | 1 | `0x008861F6` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x008862C9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
  [   0] wField_05                      u16
```

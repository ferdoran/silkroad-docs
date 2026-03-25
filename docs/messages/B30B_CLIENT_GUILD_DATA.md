# CLIENT_GUILD_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB30B` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x00886000` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0088605B` |
| 2 | `dwField_02` | `u32` | 4 | `0x00886069` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 10 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] wField_03                      u16
  [  10] bytesData_3                    bytes  (variable length)
```

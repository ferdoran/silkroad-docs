# CLIENT_GUILD_REQUEST_2

| Property | Value |
|----------|-------|
| Opcode | `0xB308` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x00882030` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088203E` |
| 2 | `byField_02` | `u8` | 1 | `0x009976E1` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00997729` |
| 4 | `bytesData_3` | `bytes` | variable | `0x00997767` |
| 5 | `dwField_05` | `u32` | 4 | `0x00997775` |
| 6 | `dwField_06` | `u32` | 4 | `0x00997783` |
| 7 | `byField_07` | `u8` | 1 | `0x00997791` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] bytesData_2                    bytes  (variable length)
  [   0] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] dwField_06                     u32
  [   8] byField_07                     u8
```

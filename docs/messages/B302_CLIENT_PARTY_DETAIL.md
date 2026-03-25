# CLIENT_PARTY_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB302` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x0087FDD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x009993F1` |
| 2 | `dwField_02` | `u32` | 4 | `0x00999439` |
| 3 | `wField_03` | `u16` | 2 | `0x00999447` |
| 4 | `bytesData_3` | `bytes` | variable | `0x00999489` |
| 5 | `dwField_05` | `u32` | 4 | `0x00999497` |
| 6 | `byField_06` | `u8` | 1 | `0x009994A5` |

**Minimum size**: 12 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] byField_06                     u8
```

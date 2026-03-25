# CLIENT_TITLE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0E4` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00889370` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008893B2` |
| 2 | `byField_02` | `u8` | 1 | `0x008893FE` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x0088960A` |
| 6 | `byField_06` | `u8` | 1 | `0x00889618` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
  [   0] wField_05                      u16
  [   2] byField_06                     u8
```

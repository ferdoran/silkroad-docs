# SERVER_SIEGE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30EF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00885C20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885C5F` |
| 2 | `byField_02` | `u8` | 1 | `0x00885C7F` |
| 3 | `dwField_03` | `u32` | 4 | `0x00885D1F` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `dwField_06` | `u32` | 4 | `0x00885D3B` |
| 7 | `byField_07` | `u8` | 1 | `0x00885D49` |
| 8 | `wField_08` | `u16` | 2 | `0x00885E0A` |

**Minimum size**: 15 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] wField_04                      u16
  [   8] bytesData_4                    bytes  (variable length)
  [   0] dwField_06                     u32
  [   4] byField_07                     u8
  [   5] wField_08                      u16
```

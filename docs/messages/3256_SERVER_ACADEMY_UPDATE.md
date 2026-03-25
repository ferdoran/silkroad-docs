# SERVER_ACADEMY_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x3256` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088F9E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088FA5D` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088FA77` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088FA85` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `wField_06` | `u16` | 2 | `0x0088FC65` |

**Minimum size**: 13 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] wField_04                      u16
  [  11] bytesData_4                    bytes  (variable length)
  [   0] wField_06                      u16
```

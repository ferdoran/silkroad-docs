# CLIENT_ACADEMY_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB251` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x0088F630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088F679` |
| 2 | `bytesData_1` | `bytes` | variable | `0x00841948` |
| 3 | `wField_03` | `u16` | 2 | `0x0088F70D` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 5 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
  [   0] wField_03                      u16
  [   2] wField_04                      u16
  [   4] bytesData_4                    bytes  (variable length)
```

# SERVER_COS_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x315A` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008992B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x008992D4` |
| 2 | `dwField_02` | `u32` | 4 | `0x008992E2` |
| 3 | `dwField_03` | `u32` | 4 | `0x008992F0` |
| 4 | `byField_04` | `u8` | 1 | `0x008992FE` |

**Minimum size**: 9 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] dwField_03                     u32
  [   8] byField_04                     u8
```

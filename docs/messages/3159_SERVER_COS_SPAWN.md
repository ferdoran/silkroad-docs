# SERVER_COS_SPAWN

| Property | Value |
|----------|-------|
| Opcode | `0x3159` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008990C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x008990E5` |
| 2 | `byField_02` | `u8` | 1 | `0x008990F3` |
| 3 | `byField_03` | `u8` | 1 | `0x00899101` |
| 4 | `wField_04` | `u16` | 2 | `0x0089911C` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089915B` |
| 6 | `dwField_06` | `u32` | 4 | `0x00899169` |

**Minimum size**: 12 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] byField_02                     u8
  [   1] byField_03                     u8
  [   2] wField_04                      u16
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
```

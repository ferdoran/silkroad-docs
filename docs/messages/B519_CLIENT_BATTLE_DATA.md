# CLIENT_BATTLE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB519` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x0089DBF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x0089DC4A` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089DD0B` |
| 3 | `bytesData_2` | `bytes` | variable | `0x0089DD18` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `bytesData_5` | `bytes` | variable | `0x0089DD64` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089DD7A` |
| 8 | `dwField_08` | `u32` | 4 | `0x0089DDB4` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089DDC2` |
| 10 | `dwField_10` | `u32` | 4 | `0x0089DDEA` |
| 11 | `bytesData_10` | `bytes` | variable | `0x0089DDF7` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089DE22` |
| 13 | `dwField_13` | `u32` | 4 | `0x0089DFA5` |

**Minimum size**: 30 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] bytesData_2                    bytes  (variable length)
  [   0] wField_04                      u16
  [   2] bytesData_4                    bytes  (variable length)
  [   0] bytesData_5                    bytes  (variable length)
  [   0] dwField_07                     u32
  [   4] dwField_08                     u32
  [   8] dwField_09                     u32
  [  12] dwField_10                     u32
  [  16] bytesData_10                   bytes  (variable length)
  [   0] dwField_12                     u32
  [   4] dwField_13                     u32
```

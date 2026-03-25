# CLIENT_ENTITY_EQUIPMENT

| Property | Value |
|----------|-------|
| Opcode | `0xB0E5` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088A130` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088A16F` |
| 2 | `byField_02` | `u8` | 1 | `0x0088A189` |
| 3 | `byField_03` | `u8` | 1 | `0x0088A197` |
| 4 | `byField_04` | `u8` | 1 | `0x0088A1A5` |
| 5 | `byField_05` | `u8` | 1 | `0x0088A210` |
| 6 | `wField_06` | `u16` | 2 | `0x0087356D` |
| 7 | `bytesData_6` | `bytes` | variable | `0x008735A9` |
| 8 | `byField_08` | `u8` | 1 | `0x0088A22C` |
| 9 | `dwField_09` | `u32` | 4 | `0x0088A23A` |
| 10 | `byField_10` | `u8` | 1 | `0x0088A248` |
| 11 | `byField_11` | `u8` | 1 | `0x0088A316` |
| 12 | `byField_12` | `u8` | 1 | `0x0088A332` |
| 13 | `dwField_13` | `u32` | 4 | `0x0088A340` |
| 14 | `wField_14` | `u16` | 2 | `0x0088A3BA` |
| 15 | `byField_15` | `u8` | 1 | `0x0088A3C8` |
| 16 | `byField_16` | `u8` | 1 | `0x0088A3D6` |

**Minimum size**: 23 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] byField_05                     u8
  [   5] wField_06                      u16
  [   7] bytesData_6                    bytes  (variable length)
  [   0] byField_08                     u8
  [   1] dwField_09                     u32
  [   5] byField_10                     u8
  [   6] byField_11                     u8
  [   7] byField_12                     u8
  [   8] dwField_13                     u32
  [  12] wField_14                      u16
  [  14] byField_15                     u8
  [  15] byField_16                     u8
```

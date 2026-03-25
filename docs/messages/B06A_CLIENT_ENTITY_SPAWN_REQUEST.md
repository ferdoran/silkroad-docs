# CLIENT_ENTITY_SPAWN_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB06A` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883F90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00883FCC` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088378D` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088379A` |
| 4 | `byField_04` | `u8` | 1 | `0x008837A7` |
| 5 | `byField_05` | `u8` | 1 | `0x008837B4` |
| 6 | `byField_06` | `u8` | 1 | `0x008837C1` |
| 7 | `byField_07` | `u8` | 1 | `0x008837CE` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `wField_10` | `u16` | 2 | `0x00884089` |

**Minimum size**: 17 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] byField_05                     u8
  [  11] byField_06                     u8
  [  12] byField_07                     u8
  [  13] wField_08                      u16
  [  15] bytesData_8                    bytes  (variable length)
  [   0] wField_10                      u16
```

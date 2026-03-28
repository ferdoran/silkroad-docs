# SERVER_PARTY_UPDATE

> **Corrected name** (server RE): Was `SERVER_WORLD_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3864` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x00880010`, `0x00886B10` |

## Handler 1: `0x00880010`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088001F` |
| 2 | `dwField_02` | `u32` | 4 | `0x00880054` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

## Handler 2: `0x00886B10`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00886B5B` |
| 2 | `byField_02` | `u8` | 1 | `0x00883638` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088364B` |
| 4 | `wField_04` | `u16` | 2 | `0x0087356D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x008735A9` |
| 6 | `dwField_06` | `u32` | 4 | `0x00883668` |
| 7 | `byField_07` | `u8` | 1 | `0x0088367A` |
| 8 | `byField_08` | `u8` | 1 | `0x0088368C` |
| 9 | `wField_09` | `u16` | 2 | `0x008836A4` |
| 10 | `dwField_10` | `u32` | 4 | `0x008836B9` |
| 11 | `dwField_11` | `u32` | 4 | `0x008836C6` |
| 12 | `dwField_12` | `u32` | 4 | `0x008836D3` |
| 13 | `wField_13` | `u16` | 2 | `0x008836F9` |
| 14 | `wField_14` | `u16` | 2 | `0x00883703` |
| 15 | `wField_15` | `u16` | 2 | `0x0088370D` |
| 16 | `dwField_16` | `u32` | 4 | `0x00883726` |
| 17 | `byField_17` | `u8` | 1 | `0x00883747` |
| 18 | `dwField_18` | `u32` | 4 | `0x00883759` |
| 19 | `dwField_19` | `u32` | 4 | `0x00883766` |
| 20 | `dwField_20` | `u32` | 4 | `0x00886D53` |
| 21 | `byField_21` | `u8` | 1 | `0x00886D61` |
| 22 | `dwField_22` | `u32` | 4 | `0x00886FA0` |
| 23 | `wField_23` | `u16` | 2 | `0x00887130` |
| 24 | `dwField_24` | `u32` | 4 | `0x008871E1` |

**Minimum size**: 62 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] wField_04                      u16
  [   8] bytesData_4                    bytes  (variable length)
  [   0] dwField_06                     u32
  [   4] byField_07                     u8
  [   5] byField_08                     u8
  [   6] wField_09                      u16
  [   8] dwField_10                     u32
  [  12] dwField_11                     u32
  [  16] dwField_12                     u32
  [  20] wField_13                      u16
  [  22] wField_14                      u16
  [  24] wField_15                      u16
  [  26] dwField_16                     u32
  [  30] byField_17                     u8
  [  31] dwField_18                     u32
  [  35] dwField_19                     u32
  [  39] dwField_20                     u32
  [  43] byField_21                     u8
  [  44] dwField_22                     u32
  [  48] wField_23                      u16
  [  50] dwField_24                     u32
```

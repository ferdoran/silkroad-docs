# CLIENT_WORLD_SPAWN_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB06D` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00884660` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008846CC` |
| 2 | `dwField_02` | `u32` | 4 | `0x008846DA` |
| 3 | `dwField_03` | `u32` | 4 | `0x008846E8` |
| 4 | `dwField_04` | `u32` | 4 | `0x008846F6` |
| 5 | `dwField_05` | `u32` | 4 | `0x00884704` |
| 6 | `byField_06` | `u8` | 1 | `0x00884712` |
| 7 | `byField_07` | `u8` | 1 | `0x00883638` |
| 8 | `dwField_08` | `u32` | 4 | `0x0088364B` |
| 9 | `wField_09` | `u16` | 2 | `0x0087356D` |
| 10 | `bytesData_9` | `bytes` | variable | `0x008735A9` |
| 11 | `dwField_11` | `u32` | 4 | `0x00883668` |
| 12 | `byField_12` | `u8` | 1 | `0x0088367A` |
| 13 | `byField_13` | `u8` | 1 | `0x0088368C` |
| 14 | `wField_14` | `u16` | 2 | `0x008836A4` |
| 15 | `dwField_15` | `u32` | 4 | `0x008836B9` |
| 16 | `dwField_16` | `u32` | 4 | `0x008836C6` |
| 17 | `dwField_17` | `u32` | 4 | `0x008836D3` |
| 18 | `wField_18` | `u16` | 2 | `0x008836F9` |
| 19 | `wField_19` | `u16` | 2 | `0x00883703` |
| 20 | `wField_20` | `u16` | 2 | `0x0088370D` |
| 21 | `dwField_21` | `u32` | 4 | `0x00883726` |
| 22 | `byField_22` | `u8` | 1 | `0x00883747` |
| 23 | `dwField_23` | `u32` | 4 | `0x00883759` |
| 24 | `dwField_24` | `u32` | 4 | `0x00883766` |

**Minimum size**: 67 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] dwField_05                     u32
  [  20] byField_06                     u8
  [  21] byField_07                     u8
  [  22] dwField_08                     u32
  [  26] wField_09                      u16
  [  28] bytesData_9                    bytes  (variable length)
  [   0] dwField_11                     u32
  [   4] byField_12                     u8
  [   5] byField_13                     u8
  [   6] wField_14                      u16
  [   8] dwField_15                     u32
  [  12] dwField_16                     u32
  [  16] dwField_17                     u32
  [  20] wField_18                      u16
  [  22] wField_19                      u16
  [  24] wField_20                      u16
  [  26] dwField_21                     u32
  [  30] byField_22                     u8
  [  31] dwField_23                     u32
  [  35] dwField_24                     u32
```

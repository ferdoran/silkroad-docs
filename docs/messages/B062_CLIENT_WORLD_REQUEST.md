# CLIENT_WORLD_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB062` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883CC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byMemberCount` | `u8` | 1 | `0x00883D05` |
| 2 | `dwPartyID` | `u32` | 4 | `0x00883D28` |
| 3 | `dwLeaderID` | `u32` | 4 | `0x00883D50` |
| 4 | `byLevel` | `u8` | 1 | `0x00883D5E` |
| 5 | `byMemberType` | `u8` | 1 | `0x00883E2E` |
| 6 | `byField_06` | `u8` | 1 | `0x00883638` |
| 7 | `dwField_07` | `u32` | 4 | `0x0088364B` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `dwField_10` | `u32` | 4 | `0x00883668` |
| 11 | `byField_11` | `u8` | 1 | `0x0088367A` |
| 12 | `byField_12` | `u8` | 1 | `0x0088368C` |
| 13 | `wField_13` | `u16` | 2 | `0x008836A4` |
| 14 | `dwField_14` | `u32` | 4 | `0x008836B9` |
| 15 | `dwField_15` | `u32` | 4 | `0x008836C6` |
| 16 | `dwField_16` | `u32` | 4 | `0x008836D3` |
| 17 | `wField_17` | `u16` | 2 | `0x008836F9` |
| 18 | `wField_18` | `u16` | 2 | `0x00883703` |
| 19 | `wField_19` | `u16` | 2 | `0x0088370D` |
| 20 | `dwField_20` | `u32` | 4 | `0x00883726` |
| 21 | `byField_21` | `u8` | 1 | `0x00883747` |
| 22 | `dwField_22` | `u32` | 4 | `0x00883759` |
| 23 | `dwField_23` | `u32` | 4 | `0x00883766` |

**Minimum size**: 57 bytes + variable fields

### Structure Summary

```
  [   0] byMemberCount                  u8
  [   1] dwPartyID                      u32
  [   5] dwLeaderID                     u32
  [   9] byLevel                        u8
  [  10] byMemberType                   u8
  [  11] byField_06                     u8
  [  12] dwField_07                     u32
  [  16] wField_08                      u16
  [  18] bytesData_8                    bytes  (variable length)
  [   0] dwField_10                     u32
  [   4] byField_11                     u8
  [   5] byField_12                     u8
  [   6] wField_13                      u16
  [   8] dwField_14                     u32
  [  12] dwField_15                     u32
  [  16] dwField_16                     u32
  [  20] wField_17                      u16
  [  22] wField_18                      u16
  [  24] wField_19                      u16
  [  26] dwField_20                     u32
  [  30] byField_21                     u8
  [  31] dwField_22                     u32
  [  35] dwField_23                     u32
```

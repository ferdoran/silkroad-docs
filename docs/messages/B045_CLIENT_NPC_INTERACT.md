# CLIENT_NPC_INTERACT

| Property | Value |
|----------|-------|
| Opcode | `0xB045` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A9E30` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A9E6F` |
| 2 | `wField_02` | `u16` | 2 | `0x008A9E7D` |
| 3 | `byField_03` | `u8` | 1 | `0x008A9EBF` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A9ED6` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A9EF0` |
| 6 | `wField_06` | `u16` | 2 | `0x008A9F0A` |
| 7 | `byField_07` | `u8` | 1 | `0x008A9F5D` |
| 8 | `dwField_08` | `u32` | 4 | `0x008A9F8F` |
| 9 | `dwField_09` | `u32` | 4 | `0x008AA16B` |
| 10 | `wField_10` | `u16` | 2 | `0x008AA1D1` |
| 11 | `dwField_11` | `u32` | 4 | `0x008AA22C` |
| 12 | `dwField_12` | `u32` | 4 | `0x008AB134` |
| 13 | `dwField_13` | `u32` | 4 | `0x008AB249` |
| 14 | `dwField_14` | `u32` | 4 | `0x008AB2BF` |
| 15 | `byField_15` | `u8` | 1 | `0x008AB2D9` |
| 16 | `dwField_16` | `u32` | 4 | `0x008AB309` |
| 17 | `byField_17` | `u8` | 1 | `0x009D2326` |

**Total size**: 50 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wField_02                      u16
  [   6] byField_03                     u8
  [   7] dwField_04                     u32
  [  11] dwField_05                     u32
  [  15] wField_06                      u16
  [  17] byField_07                     u8
  [  18] dwField_08                     u32
  [  22] dwField_09                     u32
  [  26] wField_10                      u16
  [  28] dwField_11                     u32
  [  32] dwField_12                     u32
  [  36] dwField_13                     u32
  [  40] dwField_14                     u32
  [  44] byField_15                     u8
  [  45] dwField_16                     u32
  [  49] byField_17                     u8
```

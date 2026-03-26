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
| 2 | `wFlags` | `u16` | 2 | `0x008A9E7D` |
| 3 | `byHasUpdate` | `u8` | 1 | `0x008A9EBF` |
| 4 | `dwParam1` | `u32` | 4 | `0x008A9ED6` |
| 5 | `dwParam2` | `u32` | 4 | `0x008A9EF0` |
| 6 | `wStatusFlags` | `u16` | 2 | `0x008A9F0A` |
| 7 | `byStateFlags` | `u8` | 1 | `0x008A9F5D` |
| 8 | `dwStateParam` | `u32` | 4 | `0x008A9F8F` |
| 9 | `dwAutoPotion` | `u32` | 4 | `0x008AA16B` |
| 10 | `wBuffFlags` | `u16` | 2 | `0x008AA1D1` |
| 11 | `dwAbnormalState` | `u32` | 4 | `0x008AA22C` |
| 12 | `dwField_12` | `u32` | 4 | `0x008AB134` |
| 13 | `dwField_13` | `u32` | 4 | `0x008AB249` |
| 14 | `dwField_14` | `u32` | 4 | `0x008AB2BF` |
| 15 | `byField_15` | `u8` | 1 | `0x008AB2D9` |
| 16 | `dwField_16` | `u32` | 4 | `0x008AB309` |
| 17 | `byField_17` | `u8` | 1 | `0x009D2326` |

**Total size**: 50 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_STT_FORT_ITEMUSE_INTERRUPT` | UI |

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wFlags                         u16
  [   6] byHasUpdate                    u8
  [   7] dwParam1                       u32
  [  11] dwParam2                       u32
  [  15] wStatusFlags                   u16
  [  17] byStateFlags                   u8
  [  18] dwStateParam                   u32
  [  22] dwAutoPotion                   u32
  [  26] wBuffFlags                     u16
  [  28] dwAbnormalState                u32
  [  32] dwField_12                     u32
  [  36] dwField_13                     u32
  [  40] dwField_14                     u32
  [  44] byField_15                     u8
  [  45] dwField_16                     u32
  [  49] byField_17                     u8
```

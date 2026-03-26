# CLIENT_ENTITY_DETAIL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB0F1` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00887330` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088737B` |
| 2 | `dwGuildID` | `u32` | 4 | `0x0088753B` |
| 3 | `byRace` | `u16` | 2 | `0x004F7A7D` |
| 4 | `byLevel` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwGP1` | `u8` | 1 | `0x00887558` |
| 6 | `dwGP2` | `u8` | 1 | `0x00887566` |
| 7 | `dwGP3` | `u32` | 4 | `0x00887574` |
| 8 | `dwGP4` | `u32` | 4 | `0x00887582` |
| 9 | `dwGoldStored` | `u32` | 4 | `0x00887590` |
| 10 | `dwGoldLimit` | `u32` | 4 | `0x0088759E` |
| 11 | `byMemberCount` | `u32` | 4 | `0x008875AC` |
| 12 | `byMemberFlags` | `u32` | 4 | `0x008875C9` |
| 13 | `dwMemberData` | `u8` | 1 | `0x008875D7` |
| 14 | `byMemberRole` | `u8` | 1 | `0x008875E5` |
| 15 | `dwMemberParam` | `u32` | 4 | `0x00887747` |
| 16 | `byMemberLevel` | `u8` | 1 | `0x00887807` |
| 17 | `byMemberExtra1` | `u32` | 4 | `0x008879DC` |
| 18 | `dwMemberUID` | `u8` | 1 | `0x008879EA` |
| 19 | `dwMemberAssoc` | `u8` | 1 | `0x005BB24E` |
| 20 | `byFlagByte1` | `u8` | 1 | `0x005BB276` |
| 21 | `byFlagByte2` | `u8` | 1 | `0x005BB683` |
| 22 | `dwExtraUID` | `u32` | 4 | `0x005BB86D` |
| 23 | `dwExtraParam1` | `u32` | 4 | `0x005BB890` |
| 24 | `byExtraFlags` | `u8` | 1 | `0x00887A1A` |
| 25 | `dwExtraParam2` | `u32` | 4 | `0x00887A39` |
| 26 | `byExtraRole` | `u32` | 4 | `0x00887A47` |
| 27 | `byField_27` | `u8` | 1 | `0x00887A75` |
| 28 | `byField_28` | `u8` | 1 | `0x00887A83` |
| 29 | `dwField_29` | `u32` | 4 | `0x00887AA9` |

**Minimum size**: 71 bytes + variable fields

### Structure Summary

```
  [   0] byType                         u8
  [   1] dwGuildID                      u32
  [   5] byRace                         u16
  [   7] byLevel                        bytes  (variable length)
  [   0] dwGP1                          u8
  [   1] dwGP2                          u8
  [   2] dwGP3                          u32
  [   6] dwGP4                          u32
  [  10] dwGoldStored                   u32
  [  14] dwGoldLimit                    u32
  [  18] byMemberCount                  u32
  [  22] byMemberFlags                  u32
  [  26] dwMemberData                   u8
  [  27] byMemberRole                   u8
  [  28] dwMemberParam                  u32
  [  32] byMemberLevel                  u8
  [  33] byMemberExtra1                 u32
  [  37] dwMemberUID                    u8
  [  38] dwMemberAssoc                  u8
  [  39] byFlagByte1                    u8
  [  40] byFlagByte2                    u8
  [  41] dwExtraUID                     u32
  [  45] dwExtraParam1                  u32
  [  49] byExtraFlags                   u8
  [  50] dwExtraParam2                  u32
  [  54] byExtraRole                    u32
  [  58] byField_27                     u8
  [  59] byField_28                     u8
  [  60] dwField_29                     u32
```

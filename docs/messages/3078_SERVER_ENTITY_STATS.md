# SERVER_ENTITY_STATS

| Property | Value |
|----------|-------|
| Opcode | `0x3078` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00878B40` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byStatType` | `u8` | 1 | `0x00878BA4` |
| 2 | `byAction` | `u8` | 1 | `0x00878BB2` |
| 3 | `wMinPhyAtk` | `u16` | 2 | `0x00878BC8` |
| 4 | `dwMaxPhyAtk` | `u32` | 4 | `0x004F74CA` |
| 5 | `wMinMagAtk` | `u16` | 2 | `0x004F744A` |
| 6 | `ullHP` | `u64` | 8 | `0x005E8BDA` |
| 7 | `byStr` | `u8` | 1 | `0x004F746A` |
| 8 | `byInt` | `u8` | 1 | `0x00878D91` |
| 9 | `byStatPoint_01` | `u8` | 1 | `0x00878DAB` |
| 10 | `byStatPoint_02` | `u8` | 1 | `0x00878DC5` |
| 11 | `byStatPoint_03` | `u8` | 1 | `0x00878DDF` |
| 12 | `byStatPoint_04` | `u8` | 1 | `0x00878DF9` |
| 13 | `byStatPoint_05` | `u8` | 1 | `0x00878E13` |
| 14 | `byStatPoint_06` | `u8` | 1 | `0x00878E2D` |
| 15 | `byStatPoint_07` | `u8` | 1 | `0x00878E47` |
| 16 | `byStatPoint_08` | `u8` | 1 | `0x00878E61` |
| 17 | `byStatPoint_09` | `u8` | 1 | `0x00878E7B` |
| 18 | `byStatPoint_10` | `u8` | 1 | `0x00878EA8` |
| 19 | `byStatPoint_11` | `u8` | 1 | `0x00878EC2` |
| 20 | `byStatPoint_12` | `u8` | 1 | `0x00878EDC` |
| 21 | `byStatPoint_13` | `u8` | 1 | `0x00878EF6` |
| 22 | `byStatPoint_14` | `u8` | 1 | `0x00878F10` |
| 23 | `byStatPoint_15` | `u8` | 1 | `0x00878F2A` |
| 24 | `byStatPoint_16` | `u8` | 1 | `0x00878F44` |
| 25 | `byStatPoint_17` | `u8` | 1 | `0x00878F5E` |
| 26 | `byStatPoint_18` | `u8` | 1 | `0x00878F78` |
| 27 | `byStatPoint_19` | `u8` | 1 | `0x00878F92` |
| 28 | `byStatPoint_20` | `u8` | 1 | `0x00878FAC` |
| 29 | `byStatPoint_21` | `u8` | 1 | `0x00878FC6` |
| 30 | `byStatPoint_22` | `u8` | 1 | `0x00878FE0` |
| 31 | `byStatPoint_23` | `u8` | 1 | `0x00878FFA` |
| 32 | `byStatPoint_24` | `u8` | 1 | `0x00879014` |
| 33 | `byStatPoint_25` | `u8` | 1 | `0x0087902E` |
| 34 | `byStatPoint_26` | `u16` | 2 | `0x004F74AA` |

**Total size**: 47 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_FORT_MANAGER_TAXLEVY_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_CONSTRUCTION_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_UPGRADE_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_REPAIR_COMPLETE` | UI |
| `UIIT_MSG_FORT_COMMON_DISMISS_COMPLETE` | UI |
| `UIIT_MSG_GUILD_INTRODUCE_CHANGE` | UI |
| `UIIT_MSG_FORTRESS_BUFF` | UI |

### Structure Summary

```
  [   0] byStatType                     u8
  [   1] byAction                       u8
  [   2] wMinPhyAtk                     u16
  [   4] dwMaxPhyAtk                    u32
  [   8] wMinMagAtk                     u16
  [  10] ullHP                          u64
  [  18] byStr                          u8
  [  19] byInt                          u8
  [  20] byStatPoint_01                 u8
  [  21] byStatPoint_02                 u8
  [  22] byStatPoint_03                 u8
  [  23] byStatPoint_04                 u8
  [  24] byStatPoint_05                 u8
  [  25] byStatPoint_06                 u8
  [  26] byStatPoint_07                 u8
  [  27] byStatPoint_08                 u8
  [  28] byStatPoint_09                 u8
  [  29] byStatPoint_10                 u8
  [  30] byStatPoint_11                 u8
  [  31] byStatPoint_12                 u8
  [  32] byStatPoint_13                 u8
  [  33] byStatPoint_14                 u8
  [  34] byStatPoint_15                 u8
  [  35] byStatPoint_16                 u8
  [  36] byStatPoint_17                 u8
  [  37] byStatPoint_18                 u8
  [  38] byStatPoint_19                 u8
  [  39] byStatPoint_20                 u8
  [  40] byStatPoint_21                 u8
  [  41] byStatPoint_22                 u8
  [  42] byStatPoint_23                 u8
  [  43] byStatPoint_24                 u8
  [  44] byStatPoint_25                 u8
  [  45] byStatPoint_26                 u16
```

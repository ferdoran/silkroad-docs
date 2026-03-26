# SERVER_ENTITY_UPDATE_EQUIPMENT

| Property | Value |
|----------|-------|
| Opcode | `0x30E7` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008AA340` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008AA382` |
| 2 | `byUpdateType` | `u8` | 1 | `0x008AA390` |
| 3 | `bySlot` | `u8` | 1 | `0x008AA41D` |
| 4 | `byItemType` | `u8` | 1 | `0x008AA454` |
| 5 | `byGrade` | `u8` | 1 | `0x008AA46D` |
| 6 | `dwRefItemID` | `u32` | 4 | `0x008BB144` |
| 7 | `wOptLevel` | `u16` | 2 | `0x008BB174` |
| 8 | `dwDurability` | `u32` | 4 | `0x008BB192` |
| 9 | `dwMaxDurability` | `u32` | 4 | `0x008BB1A0` |
| 10 | `wMagicOptCount` | `u16` | 2 | `0x008BB1C4` |
| 11 | `dwMagicOpt1` | `u32` | 4 | `0x008BB1DE` |
| 12 | `dwMagicOpt2` | `u32` | 4 | `0x008BE549` |
| 13 | `byBound` | `u8` | 1 | `0x008BE5DD` |
| 14 | `ullOwnerUID` | `u64` | 8 | `0x008BE5ED` |
| 15 | `dwQuantity` | `u32` | 4 | `0x008BE5FB` |
| 16 | `bytesCreator` | `bytes` | variable | `0x008BE642` |
| 17 | `ullTimestamp` | `u64` | 8 | `0x008BE652` |
| 18 | `dwRentalData` | `u32` | 4 | `0x008BE662` |
| 19 | `byRentalFlag` | `u8` | 1 | `0x008BCE4B` |
| 20 | `ullRentalTime` | `u64` | 8 | `0x008BCE9F` |
| 21 | `byArmorSlot` | `u8` | 1 | `0x008BB08E` |
| 22 | `byWeaponSlot` | `u8` | 1 | `0x008BB09C` |
| 23 | `byItemGrade` | `u8` | 1 | `0x008BB0BA` |
| 24 | `ullSerialNum` | `u64` | 8 | `0x008BB0C8` |
| 25 | `wVarParam1` | `u16` | 2 | `0x008BE6C9` |
| 26 | `wVarParam2` | `u16` | 2 | `0x004F7A7D` |
| 27 | `bytesSocket` | `bytes` | variable | `0x004F7AB9` |
| 28 | `dwSellPrice` | `u32` | 4 | `0x004F74CA` |
| 29 | `wStackMax` | `u16` | 2 | `0x008BE75F` |
| 30 | `byTradeable` | `u8` | 1 | `0x004F746A` |
| 31 | `byDroppable` | `u8` | 1 | `0x008BE830` |
| 32 | `dwExpire` | `u32` | 4 | `0x008BE849` |
| 33 | `dwCooldown` | `u32` | 4 | `0x008BE8F9` |
| 34 | `byUseFlag` | `u8` | 1 | `0x008BE927` |
| 35 | `byExtraFlag` | `u8` | 1 | `0x008BE97D` |
| 36 | `dwExtra1` | `u32` | 4 | `0x008BE98B` |
| 37 | `dwExtra2` | `u32` | 4 | `0x008BE999` |
| 38 | `dwExtra3` | `u32` | 4 | `0x008BE9DA` |
| 39 | `byReserved` | `u8` | 1 | `0x008BE9E8` |
| 40 | `dwFlags` | `u32` | 4 | `0x008BEAAE` |
| 41 | `ullAssoc` | `u64` | 8 | `0x008AA4E7` |
| 42 | `dwParam1` | `u32` | 4 | `0x008AA4F5` |
| 43 | `wParam2` | `u16` | 2 | `0x008AA775` |
| 44 | `dwParam3` | `u32` | 4 | `0x008AA980` |

**Minimum size**: 134 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_COSNEWUI_TITLE` | UI |

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byUpdateType                   u8
  [   5] bySlot                         u8
  [   6] byItemType                     u8
  [   7] byGrade                        u8
  [   8] dwRefItemID                    u32
  [  12] wOptLevel                      u16
  [  14] dwDurability                   u32
  [  18] dwMaxDurability                u32
  [  22] wMagicOptCount                 u16
  [  24] dwMagicOpt1                    u32
  [  28] dwMagicOpt2                    u32
  [  32] byBound                        u8
  [  33] ullOwnerUID                    u64
  [  41] dwQuantity                     u32
  [  45] bytesCreator                   bytes  (variable length)
  [   0] ullTimestamp                   u64
  [   8] dwRentalData                   u32
  [  12] byRentalFlag                   u8
  [  13] ullRentalTime                  u64
  [  21] byArmorSlot                    u8
  [  22] byWeaponSlot                   u8
  [  23] byItemGrade                    u8
  [  24] ullSerialNum                   u64
  [  32] wVarParam1                     u16
  [  34] wVarParam2                     u16
  [  36] bytesSocket                    bytes  (variable length)
  [   0] dwSellPrice                    u32
  [   4] wStackMax                      u16
  [   6] byTradeable                    u8
  [   7] byDroppable                    u8
  [   8] dwExpire                       u32
  [  12] dwCooldown                     u32
  [  16] byUseFlag                      u8
  [  17] byExtraFlag                    u8
  [  18] dwExtra1                       u32
  [  22] dwExtra2                       u32
  [  26] dwExtra3                       u32
  [  30] byReserved                     u8
  [  31] dwFlags                        u32
  [  35] ullAssoc                       u64
  [  43] dwParam1                       u32
  [  47] wParam2                        u16
  [  49] dwParam3                       u32
```

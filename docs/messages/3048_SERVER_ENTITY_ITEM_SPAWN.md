# SERVER_ENTITY_ITEM_SPAWN

| Property | Value |
|----------|-------|
| Opcode | `0x3048` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A8C10` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A8C7F` |
| 2 | `byItemType` | `u8` | 1 | `0x008A8C99` |
| 3 | `byEquipSlot` | `u8` | 1 | `0x008A8CB9` |
| 4 | `dwRefItemID` | `u32` | 4 | `0x008BB144` |
| 5 | `wOptLevel` | `u16` | 2 | `0x008BB174` |
| 6 | `dwDurability` | `u32` | 4 | `0x008BB192` |
| 7 | `dwMaxDurability` | `u32` | 4 | `0x008BB1A0` |
| 8 | `wMagicOptCount` | `u16` | 2 | `0x008BB1C4` |
| 9 | `dwMagicParam1` | `u32` | 4 | `0x008BB1DE` |
| 10 | `dwMagicParam2` | `u32` | 4 | `0x008BE549` |
| 11 | `byBound` | `u8` | 1 | `0x008BE5DD` |
| 12 | `ullOwnerUID` | `u64` | 8 | `0x008BE5ED` |
| 13 | `dwQuantity` | `u32` | 4 | `0x008BE5FB` |
| 14 | `bytesCreator` | `bytes` | variable | `0x008BE642` |
| 15 | `ullTimestamp` | `u64` | 8 | `0x008BE652` |
| 16 | `dwRentalData` | `u32` | 4 | `0x008BE662` |
| 17 | `byRentalFlag` | `u8` | 1 | `0x008BCE4B` |
| 18 | `ullRentalTime` | `u64` | 8 | `0x008BCE9F` |
| 19 | `byArmorType` | `u8` | 1 | `0x008BB08E` |
| 20 | `byWeaponType` | `u8` | 1 | `0x008BB09C` |
| 21 | `byGrade` | `u8` | 1 | `0x008BB0BA` |
| 22 | `ullSerialNum` | `u64` | 8 | `0x008BB0C8` |
| 23 | `wVarParam1` | `u16` | 2 | `0x008BE6C9` |
| 24 | `wVarParam2` | `u16` | 2 | `0x004F7A7D` |
| 25 | `bytesSocket` | `bytes` | variable | `0x004F7AB9` |
| 26 | `dwSellPrice` | `u32` | 4 | `0x004F74CA` |
| 27 | `wStackMax` | `u16` | 2 | `0x008BE75F` |
| 28 | `byTradeable` | `u8` | 1 | `0x004F746A` |
| 29 | `byDroppable` | `u8` | 1 | `0x008BE830` |
| 30 | `dwExpire` | `u32` | 4 | `0x008BE849` |
| 31 | `dwCooldown` | `u32` | 4 | `0x008BE8F9` |
| 32 | `byStorageType` | `u8` | 1 | `0x008BE927` |
| 33 | `bySlotIndex` | `u8` | 1 | `0x008BE97D` |
| 34 | `dwFlags` | `u32` | 4 | `0x008BE98B` |
| 35 | `dwExtraFlags` | `u32` | 4 | `0x008BE999` |
| 36 | `dwReserved` | `u32` | 4 | `0x008BE9DA` |
| 37 | `byReservedFlag` | `u8` | 1 | `0x008BE9E8` |
| 38 | `dwAssocID` | `u32` | 4 | `0x008BEAAE` |
| 39 | `bytesAssocData` | `bytes` | variable | `0x008416B1` |
| 40 | `bytesExtraData` | `bytes` | variable | `0x00841948` |

**Minimum size**: 111 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byItemType                     u8
  [   2] byEquipSlot                    u8
  [   3] dwRefItemID                    u32
  [   7] wOptLevel                      u16
  [   9] dwDurability                   u32
  [  13] dwMaxDurability                u32
  [  17] wMagicOptCount                 u16
  [  19] dwMagicParam1                  u32
  [  23] dwMagicParam2                  u32
  [  27] byBound                        u8
  [  28] ullOwnerUID                    u64
  [  36] dwQuantity                     u32
  [  40] bytesCreator                   bytes  (variable length)
  [   0] ullTimestamp                   u64
  [   8] dwRentalData                   u32
  [  12] byRentalFlag                   u8
  [  13] ullRentalTime                  u64
  [  21] byArmorType                    u8
  [  22] byWeaponType                   u8
  [  23] byGrade                        u8
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
  [  16] byStorageType                  u8
  [  17] bySlotIndex                    u8
  [  18] dwFlags                        u32
  [  22] dwExtraFlags                   u32
  [  26] dwReserved                     u32
  [  30] byReservedFlag                 u8
  [  31] dwAssocID                      u32
  [  35] bytesAssocData                 bytes  (variable length)
  [   0] bytesExtraData                 bytes  (variable length)
```

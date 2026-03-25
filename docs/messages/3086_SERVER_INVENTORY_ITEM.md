# SERVER_INVENTORY_ITEM

| Property | Value |
|----------|-------|
| Opcode | `0x3086` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880590` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bySlotType` | `u8` | 1 | `0x008805D9` |
| 2 | `bySlotIndex` | `u8` | 1 | `0x00880610` |
| 3 | `dwRefItemID` | `u32` | 4 | `0x008BB144` |
| 4 | `wOptLevel` | `u16` | 2 | `0x008BB174` |
| 5 | `dwDurability` | `u32` | 4 | `0x008BB192` |
| 6 | `dwMaxDurability` | `u32` | 4 | `0x008BB1A0` |
| 7 | `wMagicOptCount` | `u16` | 2 | `0x008BB1C4` |
| 8 | `dwMagicOpt1` | `u32` | 4 | `0x008BB1DE` |
| 9 | `dwMagicOpt2` | `u32` | 4 | `0x008BE549` |
| 10 | `byBound` | `u8` | 1 | `0x008BE5DD` |
| 11 | `ullOwnerUID` | `u64` | 8 | `0x008BE5ED` |
| 12 | `dwQuantity` | `u32` | 4 | `0x008BE5FB` |
| 13 | `bytesCreator` | `bytes` | variable | `0x008BE642` |
| 14 | `ullTimestamp` | `u64` | 8 | `0x008BE652` |
| 15 | `dwRentalData` | `u32` | 4 | `0x008BE662` |
| 16 | `byRentalFlag` | `u8` | 1 | `0x008BCE4B` |
| 17 | `ullRentalTime` | `u64` | 8 | `0x008BCE9F` |
| 18 | `byArmorSlot` | `u8` | 1 | `0x008BB08E` |
| 19 | `byWeaponSlot` | `u8` | 1 | `0x008BB09C` |
| 20 | `byGrade` | `u8` | 1 | `0x008BB0BA` |
| 21 | `ullSerialNum` | `u64` | 8 | `0x008BB0C8` |
| 22 | `wParam1` | `u16` | 2 | `0x008BE6C9` |
| 23 | `wParam2` | `u16` | 2 | `0x004F7A7D` |
| 24 | `bytesSocket` | `bytes` | variable | `0x004F7AB9` |
| 25 | `dwSellPrice` | `u32` | 4 | `0x004F74CA` |
| 26 | `wStackMax` | `u16` | 2 | `0x008BE75F` |
| 27 | `byTradeable` | `u8` | 1 | `0x004F746A` |
| 28 | `byDroppable` | `u8` | 1 | `0x008BE830` |
| 29 | `dwExpire` | `u32` | 4 | `0x008BE849` |
| 30 | `dwCooldown` | `u32` | 4 | `0x008BE8F9` |
| 31 | `byUseFlag` | `u8` | 1 | `0x008BE927` |
| 32 | `byExtraFlag` | `u8` | 1 | `0x008BE97D` |
| 33 | `dwExtraData1` | `u32` | 4 | `0x008BE98B` |
| 34 | `dwExtraData2` | `u32` | 4 | `0x008BE999` |
| 35 | `dwExtraData3` | `u32` | 4 | `0x008BE9DA` |
| 36 | `byReserved` | `u8` | 1 | `0x008BE9E8` |
| 37 | `dwFlags` | `u32` | 4 | `0x008BEAAE` |
| 38 | `ullAssocData` | `u64` | 8 | `0x00880658` |

**Minimum size**: 118 bytes + variable fields

### Structure Summary

```
  [   0] bySlotType                     u8
  [   1] bySlotIndex                    u8
  [   2] dwRefItemID                    u32
  [   6] wOptLevel                      u16
  [   8] dwDurability                   u32
  [  12] dwMaxDurability                u32
  [  16] wMagicOptCount                 u16
  [  18] dwMagicOpt1                    u32
  [  22] dwMagicOpt2                    u32
  [  26] byBound                        u8
  [  27] ullOwnerUID                    u64
  [  35] dwQuantity                     u32
  [  39] bytesCreator                   bytes  (variable length)
  [   0] ullTimestamp                   u64
  [   8] dwRentalData                   u32
  [  12] byRentalFlag                   u8
  [  13] ullRentalTime                  u64
  [  21] byArmorSlot                    u8
  [  22] byWeaponSlot                   u8
  [  23] byGrade                        u8
  [  24] ullSerialNum                   u64
  [  32] wParam1                        u16
  [  34] wParam2                        u16
  [  36] bytesSocket                    bytes  (variable length)
  [   0] dwSellPrice                    u32
  [   4] wStackMax                      u16
  [   6] byTradeable                    u8
  [   7] byDroppable                    u8
  [   8] dwExpire                       u32
  [  12] dwCooldown                     u32
  [  16] byUseFlag                      u8
  [  17] byExtraFlag                    u8
  [  18] dwExtraData1                   u32
  [  22] dwExtraData2                   u32
  [  26] dwExtraData3                   u32
  [  30] byReserved                     u8
  [  31] dwFlags                        u32
  [  35] ullAssocData                   u64
```

# SERVER_PET_DATA

> **Corrected name** (server RE): Was `SERVER_EXCHANGE_START` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30C8` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7870` |

### Fields (Server RE)

Branching structure based on COS type (determined by `ModelID`):

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Pet/COS unique ID |
| 2 | `ModelID` | `u32` | 4 | RefObjID determines COS type |

#### Branch: Horse / Transport

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 3 | `HP` | `u32` | 4 | Current HP |
| 4 | `HPMax` | `u32` | 4 | Maximum HP |
| 5 | `InventoryCapacity` | `u8` | 1 | Inventory size (0 for horse, >0 for transport) |

If `InventoryCapacity > 0` (Transport):

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 6 | `ItemCount` | `u8` | 1 | Number of items in transport |

For each item:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `Slot` | `u8` | 1 | Inventory slot |
| - | `RentableType` | `u32` | 4 | Rental type |
| - | `RefItemID` | `u32` | 4 | Item reference ID |
| - | `Quantity` | `u16` | 2 | Stack quantity |
| - | `OwnerName` | `ascii` | var | Item owner name |

#### Branch: Attack Pet

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 3 | `HP` | `u32` | 4 | Current HP |
| 4 | `HPMax` | `u32` | 4 | Maximum HP — from `COSData` RTTI |
| 5 | `Exp` | `u64` | 8 | Pet experience |
| 6 | `Level` | `u8` | 1 | Pet level |
| 7 | `HGP` | `u16` | 2 | Hunger Gauge Points |
| 8 | `SettingsFlags` | `u32` | 4 | Pet behavior settings |
| 9 | `Name` | `ascii` | var | Pet name |
| 10 | `PetState` | `u8` | 1 | Pet state flag (0=idle, 1=following, 2=attacking) |
| 11 | `OwnerUniqueID` | `u32` | 4 | Owner entity ID |
| 12 | `IsSelected` | `u8` | 1 | Whether this COS is the active/selected one |

#### Branch: Pick Pet

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 3 | `HP` | `u32` | 4 | Current HP — from `COSData` RTTI |
| 4 | `HPMax` | `u32` | 4 | Maximum HP — from `COSData` RTTI |
| 5 | `SettingsFlags` | `u32` | 4 | Pet behavior settings |
| 6 | `Name` | `ascii` | var | Pet name |
| 7 | `InventoryCapacity` | `u8` | 1 | Inventory size |
| 8 | `ItemCount` | `u8` | 1 | Number of items |

For each item: `u8 Slot` + [ItemData](../systems/item_structure.md)

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] ModelID                        u32

  IF isHorse || isTransport:
    [   8] HP                           u32
    [  12] HPMax                        u32
    [  16] InventoryCapacity            u8
    if InventoryCapacity > 0:           // Transport
      [  17] ItemCount                  u8
      for each:
        Slot                            u8
        RentableType                    u32
        RefItemID                       u32
        Quantity                        u16
        OwnerName                       ascii

  ELIF isAttackPet:
    [   8] HP                           u32
    [  12] HPMax                        u32       // COSData
    [  16] Exp                          u64
    [  24] Level                        u8
    [  25] HGP                          u16
    [  27] SettingsFlags                u32
    [  31] Name                         ascii
    [   ?] PetState                     u8
    [   ?] OwnerUniqueID                u32
    [   ?] IsSelected                   u8

  ELIF isPickPet:
    [   8] HP                           u32       // COSData
    [  12] HPMax                        u32       // COSData
    [  16] SettingsFlags                u32
    [  20] Name                         ascii
    [   ?] InventoryCapacity            u8
    [   ?] ItemCount                    u8
    for each:
      Slot                              u8
      ItemData                          (variable)
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A787F` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A782E` |
| 3 | `dwParam1` | `u32` | 4 | `0x008A783C` |
| 4 | `dwParam2` | `u32` | 4 | `0x008A784A` |
| 5 | `byFlag` | `u8` | 1 | `0x008A7858` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

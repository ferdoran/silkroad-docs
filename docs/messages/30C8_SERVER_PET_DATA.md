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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetDataHorseTransport {
        uint32_t HP;
        uint32_t HPMax;
        uint8_t InventoryCapacity;
        uint8_t ItemCount;
        uint8_t Slot;
        uint32_t RentableType;
        uint32_t RefItemID;
        uint16_t Quantity;
        std::string OwnerName;
    };
    struct PetDataAttackPet {
        uint32_t HP;
        uint32_t HPMax;
        uint64_t Exp;
        uint8_t Level;
        uint16_t HGP;
        uint32_t SettingsFlags;
        std::string Name;
        uint8_t PetState;
        uint32_t OwnerUniqueID;
        uint8_t IsSelected;
    };
    struct PetDataPickPet {
        uint32_t HP;
        uint32_t HPMax;
        uint32_t SettingsFlags;
        std::string Name;
        uint8_t InventoryCapacity;
        uint8_t ItemCount;
    };
    struct PetData {
        uint32_t UniqueID;
        uint32_t ModelID;
        std::variant<PetDataHorseTransport, PetDataAttackPet, PetDataPickPet> body;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public abstract record PetDataBody;
    public record PetDataHorseTransport(uint HP, uint HPMax, byte InventoryCapacity, byte ItemCount, byte Slot, uint RentableType, uint RefItemID, ushort Quantity, string OwnerName) : PetDataBody;
    public record PetDataAttackPet(uint HP, uint HPMax, ulong Exp, byte Level, ushort HGP, uint SettingsFlags, string Name, byte PetState, uint OwnerUniqueID, byte IsSelected) : PetDataBody;
    public record PetDataPickPet(uint HP, uint HPMax, uint SettingsFlags, string Name, byte InventoryCapacity, byte ItemCount) : PetDataBody;
    public record PetData(uint UniqueID, uint ModelID, PetDataBody Body);
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetDataHorseTransport {
        pub hp: u32,
        pub hpmax: u32,
        pub inventory_capacity: u8,
        pub item_count: u8,
        pub slot: u8,
        pub rentable_type: u32,
        pub ref_item_id: u32,
        pub quantity: u16,
        pub owner_name: String,
    }
    pub struct PetDataAttackPet {
        pub hp: u32,
        pub hpmax: u32,
        pub exp: u64,
        pub level: u8,
        pub hgp: u16,
        pub settings_flags: u32,
        pub name: String,
        pub pet_state: u8,
        pub owner_unique_id: u32,
        pub is_selected: u8,
    }
    pub struct PetDataPickPet {
        pub hp: u32,
        pub hpmax: u32,
        pub settings_flags: u32,
        pub name: String,
        pub inventory_capacity: u8,
        pub item_count: u8,
    }
    pub enum PetDataBody {
        HorseTransport(PetDataHorseTransport),
        AttackPet(PetDataAttackPet),
        PickPet(PetDataPickPet),
    }
    pub struct PetData {
        pub unique_id: u32,
        pub model_id: u32,
        pub body: PetDataBody,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetDataBody interface { petDataBody() }
    type PetDataHorseTransport struct {
        HP uint32
        HPMax uint32
        InventoryCapacity uint8
        ItemCount uint8
        Slot uint8
        RentableType uint32
        RefItemID uint32
        Quantity uint16
        OwnerName string
    }
    func (*PetDataHorseTransport) petDataBody() {}
    type PetDataAttackPet struct {
        HP uint32
        HPMax uint32
        Exp uint64
        Level uint8
        HGP uint16
        SettingsFlags uint32
        Name string
        PetState uint8
        OwnerUniqueID uint32
        IsSelected uint8
    }
    func (*PetDataAttackPet) petDataBody() {}
    type PetDataPickPet struct {
        HP uint32
        HPMax uint32
        SettingsFlags uint32
        Name string
        InventoryCapacity uint8
        ItemCount uint8
    }
    func (*PetDataPickPet) petDataBody() {}
    type PetData struct {
        UniqueID uint32
        ModelID uint32
        Body PetDataBody
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    type PetDataBody =
        | { kind: 'HorseTransport'; hP: number; hPMax: number; inventoryCapacity: number; itemCount: number; slot: number; rentableType: number; refItemID: number; quantity: number; ownerName: string }
        | { kind: 'AttackPet'; hP: number; hPMax: number; exp: bigint; level: number; hGP: number; settingsFlags: number; name: string; petState: number; ownerUniqueID: number; isSelected: number }
        | { kind: 'PickPet'; hP: number; hPMax: number; settingsFlags: number; name: string; inventoryCapacity: number; itemCount: number };
    export interface PetData {
        uniqueID: number;
        modelID: number;
        body: PetDataBody;
    }
    ```


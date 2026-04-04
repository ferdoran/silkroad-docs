# SERVER_STORAGE_DATA_END

> Previously documented as `SERVER_ENTITY_ITEM_SPAWN` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3048` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A8C10` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 |  |
| 2 | `itemsCount` | `u8` | 1 |  |
| 3 | `slot` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

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

</details>
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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityItemSpawn {
        uint8_t byResult;
        uint8_t byItemType;
        uint8_t byEquipSlot;
        uint32_t dwRefItemID;
        uint16_t wOptLevel;
        uint32_t dwDurability;
        uint32_t dwMaxDurability;
        uint16_t wMagicOptCount;
        uint32_t dwMagicParam1;
        uint32_t dwMagicParam2;
        uint8_t byBound;
        uint64_t ullOwnerUID;
        uint32_t dwQuantity;
        std::vector<uint8_t> bytesCreator;
        uint64_t ullTimestamp;
        uint32_t dwRentalData;
        uint8_t byRentalFlag;
        uint64_t ullRentalTime;
        uint8_t byArmorType;
        uint8_t byWeaponType;
        uint8_t byGrade;
        uint64_t ullSerialNum;
        uint16_t wVarParam1;
        uint16_t wVarParam2;
        std::vector<uint8_t> bytesSocket;
        uint32_t dwSellPrice;
        uint16_t wStackMax;
        uint8_t byTradeable;
        uint8_t byDroppable;
        uint32_t dwExpire;
        uint32_t dwCooldown;
        uint8_t byStorageType;
        uint8_t bySlotIndex;
        uint32_t dwFlags;
        uint32_t dwExtraFlags;
        uint32_t dwReserved;
        uint8_t byReservedFlag;
        uint32_t dwAssocID;
        std::vector<uint8_t> bytesAssocData;
        std::vector<uint8_t> bytesExtraData;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityItemSpawn(
        byte byResult,
        byte byItemType,
        byte byEquipSlot,
        uint dwRefItemID,
        ushort wOptLevel,
        uint dwDurability,
        uint dwMaxDurability,
        ushort wMagicOptCount,
        uint dwMagicParam1,
        uint dwMagicParam2,
        byte byBound,
        ulong ullOwnerUID,
        uint dwQuantity,
        byte[] bytesCreator,
        ulong ullTimestamp,
        uint dwRentalData,
        byte byRentalFlag,
        ulong ullRentalTime,
        byte byArmorType,
        byte byWeaponType,
        byte byGrade,
        ulong ullSerialNum,
        ushort wVarParam1,
        ushort wVarParam2,
        byte[] bytesSocket,
        uint dwSellPrice,
        ushort wStackMax,
        byte byTradeable,
        byte byDroppable,
        uint dwExpire,
        uint dwCooldown,
        byte byStorageType,
        byte bySlotIndex,
        uint dwFlags,
        uint dwExtraFlags,
        uint dwReserved,
        byte byReservedFlag,
        uint dwAssocID,
        byte[] bytesAssocData,
        byte[] bytesExtraData
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityItemSpawn {
        pub by_result: u8,
        pub by_item_type: u8,
        pub by_equip_slot: u8,
        pub dw_ref_item_id: u32,
        pub w_opt_level: u16,
        pub dw_durability: u32,
        pub dw_max_durability: u32,
        pub w_magic_opt_count: u16,
        pub dw_magic_param1: u32,
        pub dw_magic_param2: u32,
        pub by_bound: u8,
        pub ull_owner_uid: u64,
        pub dw_quantity: u32,
        pub bytes_creator: Vec<u8>,
        pub ull_timestamp: u64,
        pub dw_rental_data: u32,
        pub by_rental_flag: u8,
        pub ull_rental_time: u64,
        pub by_armor_type: u8,
        pub by_weapon_type: u8,
        pub by_grade: u8,
        pub ull_serial_num: u64,
        pub w_var_param1: u16,
        pub w_var_param2: u16,
        pub bytes_socket: Vec<u8>,
        pub dw_sell_price: u32,
        pub w_stack_max: u16,
        pub by_tradeable: u8,
        pub by_droppable: u8,
        pub dw_expire: u32,
        pub dw_cooldown: u32,
        pub by_storage_type: u8,
        pub by_slot_index: u8,
        pub dw_flags: u32,
        pub dw_extra_flags: u32,
        pub dw_reserved: u32,
        pub by_reserved_flag: u8,
        pub dw_assoc_id: u32,
        pub bytes_assoc_data: Vec<u8>,
        pub bytes_extra_data: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityItemSpawn struct {
        byResult uint8
        byItemType uint8
        byEquipSlot uint8
        dwRefItemID uint32
        wOptLevel uint16
        dwDurability uint32
        dwMaxDurability uint32
        wMagicOptCount uint16
        dwMagicParam1 uint32
        dwMagicParam2 uint32
        byBound uint8
        ullOwnerUID uint64
        dwQuantity uint32
        bytesCreator []byte
        ullTimestamp uint64
        dwRentalData uint32
        byRentalFlag uint8
        ullRentalTime uint64
        byArmorType uint8
        byWeaponType uint8
        byGrade uint8
        ullSerialNum uint64
        wVarParam1 uint16
        wVarParam2 uint16
        bytesSocket []byte
        dwSellPrice uint32
        wStackMax uint16
        byTradeable uint8
        byDroppable uint8
        dwExpire uint32
        dwCooldown uint32
        byStorageType uint8
        bySlotIndex uint8
        dwFlags uint32
        dwExtraFlags uint32
        dwReserved uint32
        byReservedFlag uint8
        dwAssocID uint32
        bytesAssocData []byte
        bytesExtraData []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityItemSpawn {
        byResult: number;
        byItemType: number;
        byEquipSlot: number;
        dwRefItemID: number;
        wOptLevel: number;
        dwDurability: number;
        dwMaxDurability: number;
        wMagicOptCount: number;
        dwMagicParam1: number;
        dwMagicParam2: number;
        byBound: number;
        ullOwnerUID: bigint;
        dwQuantity: number;
        bytesCreator: Uint8Array;
        ullTimestamp: bigint;
        dwRentalData: number;
        byRentalFlag: number;
        ullRentalTime: bigint;
        byArmorType: number;
        byWeaponType: number;
        byGrade: number;
        ullSerialNum: bigint;
        wVarParam1: number;
        wVarParam2: number;
        bytesSocket: Uint8Array;
        dwSellPrice: number;
        wStackMax: number;
        byTradeable: number;
        byDroppable: number;
        dwExpire: number;
        dwCooldown: number;
        byStorageType: number;
        bySlotIndex: number;
        dwFlags: number;
        dwExtraFlags: number;
        dwReserved: number;
        byReservedFlag: number;
        dwAssocID: number;
        bytesAssocData: Uint8Array;
        bytesExtraData: Uint8Array;
    }
    ```


# SERVER_ENTITY_UPDATE_EQUIPMENT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateEquipment {
        uint32_t dwUniqueID;
        uint8_t byUpdateType;
        uint8_t bySlot;
        uint8_t byItemType;
        uint8_t byGrade;
        uint32_t dwRefItemID;
        uint16_t wOptLevel;
        uint32_t dwDurability;
        uint32_t dwMaxDurability;
        uint16_t wMagicOptCount;
        uint32_t dwMagicOpt1;
        uint32_t dwMagicOpt2;
        uint8_t byBound;
        uint64_t ullOwnerUID;
        uint32_t dwQuantity;
        std::vector<uint8_t> bytesCreator;
        uint64_t ullTimestamp;
        uint32_t dwRentalData;
        uint8_t byRentalFlag;
        uint64_t ullRentalTime;
        uint8_t byArmorSlot;
        uint8_t byWeaponSlot;
        uint8_t byItemGrade;
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
        uint8_t byUseFlag;
        uint8_t byExtraFlag;
        uint32_t dwExtra1;
        uint32_t dwExtra2;
        uint32_t dwExtra3;
        uint8_t byReserved;
        uint32_t dwFlags;
        uint64_t ullAssoc;
        uint32_t dwParam1;
        uint16_t wParam2;
        uint32_t dwParam3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateEquipment(
        uint dwUniqueID,
        byte byUpdateType,
        byte bySlot,
        byte byItemType,
        byte byGrade,
        uint dwRefItemID,
        ushort wOptLevel,
        uint dwDurability,
        uint dwMaxDurability,
        ushort wMagicOptCount,
        uint dwMagicOpt1,
        uint dwMagicOpt2,
        byte byBound,
        ulong ullOwnerUID,
        uint dwQuantity,
        byte[] bytesCreator,
        ulong ullTimestamp,
        uint dwRentalData,
        byte byRentalFlag,
        ulong ullRentalTime,
        byte byArmorSlot,
        byte byWeaponSlot,
        byte byItemGrade,
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
        byte byUseFlag,
        byte byExtraFlag,
        uint dwExtra1,
        uint dwExtra2,
        uint dwExtra3,
        byte byReserved,
        uint dwFlags,
        ulong ullAssoc,
        uint dwParam1,
        ushort wParam2,
        uint dwParam3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateEquipment {
        pub dw_unique_id: u32,
        pub by_update_type: u8,
        pub by_slot: u8,
        pub by_item_type: u8,
        pub by_grade: u8,
        pub dw_ref_item_id: u32,
        pub w_opt_level: u16,
        pub dw_durability: u32,
        pub dw_max_durability: u32,
        pub w_magic_opt_count: u16,
        pub dw_magic_opt1: u32,
        pub dw_magic_opt2: u32,
        pub by_bound: u8,
        pub ull_owner_uid: u64,
        pub dw_quantity: u32,
        pub bytes_creator: Vec<u8>,
        pub ull_timestamp: u64,
        pub dw_rental_data: u32,
        pub by_rental_flag: u8,
        pub ull_rental_time: u64,
        pub by_armor_slot: u8,
        pub by_weapon_slot: u8,
        pub by_item_grade: u8,
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
        pub by_use_flag: u8,
        pub by_extra_flag: u8,
        pub dw_extra1: u32,
        pub dw_extra2: u32,
        pub dw_extra3: u32,
        pub by_reserved: u8,
        pub dw_flags: u32,
        pub ull_assoc: u64,
        pub dw_param1: u32,
        pub w_param2: u16,
        pub dw_param3: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateEquipment struct {
        dwUniqueID uint32
        byUpdateType uint8
        bySlot uint8
        byItemType uint8
        byGrade uint8
        dwRefItemID uint32
        wOptLevel uint16
        dwDurability uint32
        dwMaxDurability uint32
        wMagicOptCount uint16
        dwMagicOpt1 uint32
        dwMagicOpt2 uint32
        byBound uint8
        ullOwnerUID uint64
        dwQuantity uint32
        bytesCreator []byte
        ullTimestamp uint64
        dwRentalData uint32
        byRentalFlag uint8
        ullRentalTime uint64
        byArmorSlot uint8
        byWeaponSlot uint8
        byItemGrade uint8
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
        byUseFlag uint8
        byExtraFlag uint8
        dwExtra1 uint32
        dwExtra2 uint32
        dwExtra3 uint32
        byReserved uint8
        dwFlags uint32
        ullAssoc uint64
        dwParam1 uint32
        wParam2 uint16
        dwParam3 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateEquipment {
        dwUniqueID: number;
        byUpdateType: number;
        bySlot: number;
        byItemType: number;
        byGrade: number;
        dwRefItemID: number;
        wOptLevel: number;
        dwDurability: number;
        dwMaxDurability: number;
        wMagicOptCount: number;
        dwMagicOpt1: number;
        dwMagicOpt2: number;
        byBound: number;
        ullOwnerUID: bigint;
        dwQuantity: number;
        bytesCreator: Uint8Array;
        ullTimestamp: bigint;
        dwRentalData: number;
        byRentalFlag: number;
        ullRentalTime: bigint;
        byArmorSlot: number;
        byWeaponSlot: number;
        byItemGrade: number;
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
        byUseFlag: number;
        byExtraFlag: number;
        dwExtra1: number;
        dwExtra2: number;
        dwExtra3: number;
        byReserved: number;
        dwFlags: number;
        ullAssoc: bigint;
        dwParam1: number;
        wParam2: number;
        dwParam3: number;
    }
    ```


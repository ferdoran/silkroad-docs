# SERVER_EXCHANGE_PLAYER_CONFIRMED

> Previously documented as `SERVER_INVENTORY_ITEM` (client-derived).

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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryItem {
        uint8_t bySlotType;
        uint8_t bySlotIndex;
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
        uint8_t byGrade;
        uint64_t ullSerialNum;
        uint16_t wParam1;
        uint16_t wParam2;
        std::vector<uint8_t> bytesSocket;
        uint32_t dwSellPrice;
        uint16_t wStackMax;
        uint8_t byTradeable;
        uint8_t byDroppable;
        uint32_t dwExpire;
        uint32_t dwCooldown;
        uint8_t byUseFlag;
        uint8_t byExtraFlag;
        uint32_t dwExtraData1;
        uint32_t dwExtraData2;
        uint32_t dwExtraData3;
        uint8_t byReserved;
        uint32_t dwFlags;
        uint64_t ullAssocData;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryItem(
        byte bySlotType,
        byte bySlotIndex,
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
        byte byGrade,
        ulong ullSerialNum,
        ushort wParam1,
        ushort wParam2,
        byte[] bytesSocket,
        uint dwSellPrice,
        ushort wStackMax,
        byte byTradeable,
        byte byDroppable,
        uint dwExpire,
        uint dwCooldown,
        byte byUseFlag,
        byte byExtraFlag,
        uint dwExtraData1,
        uint dwExtraData2,
        uint dwExtraData3,
        byte byReserved,
        uint dwFlags,
        ulong ullAssocData
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryItem {
        pub by_slot_type: u8,
        pub by_slot_index: u8,
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
        pub by_grade: u8,
        pub ull_serial_num: u64,
        pub w_param1: u16,
        pub w_param2: u16,
        pub bytes_socket: Vec<u8>,
        pub dw_sell_price: u32,
        pub w_stack_max: u16,
        pub by_tradeable: u8,
        pub by_droppable: u8,
        pub dw_expire: u32,
        pub dw_cooldown: u32,
        pub by_use_flag: u8,
        pub by_extra_flag: u8,
        pub dw_extra_data1: u32,
        pub dw_extra_data2: u32,
        pub dw_extra_data3: u32,
        pub by_reserved: u8,
        pub dw_flags: u32,
        pub ull_assoc_data: u64,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryItem struct {
        bySlotType uint8
        bySlotIndex uint8
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
        byGrade uint8
        ullSerialNum uint64
        wParam1 uint16
        wParam2 uint16
        bytesSocket []byte
        dwSellPrice uint32
        wStackMax uint16
        byTradeable uint8
        byDroppable uint8
        dwExpire uint32
        dwCooldown uint32
        byUseFlag uint8
        byExtraFlag uint8
        dwExtraData1 uint32
        dwExtraData2 uint32
        dwExtraData3 uint32
        byReserved uint8
        dwFlags uint32
        ullAssocData uint64
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryItem {
        bySlotType: number;
        bySlotIndex: number;
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
        byGrade: number;
        ullSerialNum: bigint;
        wParam1: number;
        wParam2: number;
        bytesSocket: Uint8Array;
        dwSellPrice: number;
        wStackMax: number;
        byTradeable: number;
        byDroppable: number;
        dwExpire: number;
        dwCooldown: number;
        byUseFlag: number;
        byExtraFlag: number;
        dwExtraData1: number;
        dwExtraData2: number;
        dwExtraData3: number;
        byReserved: number;
        dwFlags: number;
        ullAssocData: bigint;
    }
    ```


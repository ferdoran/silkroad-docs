# SERVER_STALL_LEAVE_RESPONSE

> Previously documented as `CLIENT_PARTY_UPDATE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB0B5` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873FF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087403B` |
| 2 | `dwStallID` | `bytes` | variable | `0x00841948` |
| 3 | `bySlotType` | `u32` | 4 | `0x008740DD` |
| 4 | `byItemType` | `u16` | 2 | `0x004F7A7D` |
| 5 | `byDurability` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byQuantity` | `u8` | 1 | `0x008740F9` |
| 7 | `wRefItemID` | `u8` | 1 | `0x00874107` |
| 8 | `ullSerialNum` | `u8` | 1 | `0x008741DE` |
| 9 | `byOptLevel` | `u32` | 4 | `0x008BB144` |
| 10 | `byExtra` | `u16` | 2 | `0x008BB174` |
| 11 | `dwPrice` | `u32` | 4 | `0x008BB192` |
| 12 | `wStackCount` | `u32` | 4 | `0x008BB1A0` |
| 13 | `wField_13` | `u16` | 2 | `0x008BB1C4` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BB1DE` |
| 15 | `dwField_15` | `u32` | 4 | `0x008BE549` |
| 16 | `byField_16` | `u8` | 1 | `0x008BE5DD` |
| 17 | `ullField_17` | `u64` | 8 | `0x008BE5ED` |
| 18 | `dwField_18` | `u32` | 4 | `0x008BE5FB` |
| 19 | `bytesData_18` | `bytes` | variable | `0x008BE642` |
| 20 | `ullField_20` | `u64` | 8 | `0x008BE652` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE662` |
| 22 | `byField_22` | `u8` | 1 | `0x008BCE4B` |
| 23 | `ullField_23` | `u64` | 8 | `0x008BCE9F` |
| 24 | `byField_24` | `u8` | 1 | `0x008BB08E` |
| 25 | `byField_25` | `u8` | 1 | `0x008BB09C` |
| 26 | `byField_26` | `u8` | 1 | `0x008BB0BA` |
| 27 | `ullField_27` | `u64` | 8 | `0x008BB0C8` |
| 28 | `wField_28` | `u16` | 2 | `0x008BE6C9` |
| 29 | `dwField_29` | `u32` | 4 | `0x004F74CA` |
| 30 | `wField_30` | `u16` | 2 | `0x008BE75F` |
| 31 | `byField_31` | `u8` | 1 | `0x004F746A` |
| 32 | `byField_32` | `u8` | 1 | `0x008BE830` |
| 33 | `dwField_33` | `u32` | 4 | `0x008BE849` |
| 34 | `dwField_34` | `u32` | 4 | `0x008BE8F9` |
| 35 | `byField_35` | `u8` | 1 | `0x008BE927` |
| 36 | `byField_36` | `u8` | 1 | `0x008BE97D` |
| 37 | `dwField_37` | `u32` | 4 | `0x008BE98B` |
| 38 | `dwField_38` | `u32` | 4 | `0x008BE999` |
| 39 | `dwField_39` | `u32` | 4 | `0x008BE9DA` |
| 40 | `byField_40` | `u8` | 1 | `0x008BE9E8` |
| 41 | `dwField_41` | `u32` | 4 | `0x008BEAAE` |
| 42 | `byField_42` | `u8` | 1 | `0x00874216` |
| 43 | `wField_43` | `u16` | 2 | `0x00874229` |
| 44 | `ullField_44` | `u64` | 8 | `0x0087423A` |
| 45 | `byField_45` | `u8` | 1 | `0x00874277` |
| 46 | `byField_46` | `u8` | 1 | `0x008742A3` |
| 47 | `dwField_47` | `u32` | 4 | `0x008742BA` |
| 48 | `wField_48` | `u16` | 2 | `0x00874349` |

**Minimum size**: 135 bytes + variable fields

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwStallID                      bytes  (variable length)
  [   0] bySlotType                     u32
  [   4] byItemType                     u16
  [   6] byDurability                   bytes  (variable length)
  [   0] byQuantity                     u8
  [   1] wRefItemID                     u8
  [   2] ullSerialNum                   u8
  [   3] byOptLevel                     u32
  [   7] byExtra                        u16
  [   9] dwPrice                        u32
  [  13] wStackCount                    u32
  [  17] wField_13                      u16
  [  19] dwField_14                     u32
  [  23] dwField_15                     u32
  [  27] byField_16                     u8
  [  28] ullField_17                    u64
  [  36] dwField_18                     u32
  [  40] bytesData_18                   bytes  (variable length)
  [   0] ullField_20                    u64
  [   8] dwField_21                     u32
  [  12] byField_22                     u8
  [  13] ullField_23                    u64
  [  21] byField_24                     u8
  [  22] byField_25                     u8
  [  23] byField_26                     u8
  [  24] ullField_27                    u64
  [  32] wField_28                      u16
  [  34] dwField_29                     u32
  [  38] wField_30                      u16
  [  40] byField_31                     u8
  [  41] byField_32                     u8
  [  42] dwField_33                     u32
  [  46] dwField_34                     u32
  [  50] byField_35                     u8
  [  51] byField_36                     u8
  [  52] dwField_37                     u32
  [  56] dwField_38                     u32
  [  60] dwField_39                     u32
  [  64] byField_40                     u8
  [  65] dwField_41                     u32
  [  69] byField_42                     u8
  [  70] wField_43                      u16
  [  72] ullField_44                    u64
  [  80] byField_45                     u8
  [  81] byField_46                     u8
  [  82] dwField_47                     u32
  [  86] wField_48                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyUpdate {
        uint8_t byAction;
        std::vector<uint8_t> dwStallID;
        uint32_t bySlotType;
        uint16_t byItemType;
        std::vector<uint8_t> byDurability;
        uint8_t byQuantity;
        uint8_t wRefItemID;
        uint8_t ullSerialNum;
        uint32_t byOptLevel;
        uint16_t byExtra;
        uint32_t dwPrice;
        uint32_t wStackCount;
        uint16_t wField_13;
        uint32_t dwField_14;
        uint32_t dwField_15;
        uint8_t byField_16;
        uint64_t ullField_17;
        uint32_t dwField_18;
        std::vector<uint8_t> bytesData_18;
        uint64_t ullField_20;
        uint32_t dwField_21;
        uint8_t byField_22;
        uint64_t ullField_23;
        uint8_t byField_24;
        uint8_t byField_25;
        uint8_t byField_26;
        uint64_t ullField_27;
        uint16_t wField_28;
        uint32_t dwField_29;
        uint16_t wField_30;
        uint8_t byField_31;
        uint8_t byField_32;
        uint32_t dwField_33;
        uint32_t dwField_34;
        uint8_t byField_35;
        uint8_t byField_36;
        uint32_t dwField_37;
        uint32_t dwField_38;
        uint32_t dwField_39;
        uint8_t byField_40;
        uint32_t dwField_41;
        uint8_t byField_42;
        uint16_t wField_43;
        uint64_t ullField_44;
        uint8_t byField_45;
        uint8_t byField_46;
        uint32_t dwField_47;
        uint16_t wField_48;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyUpdate(
        byte byAction,
        byte[] dwStallID,
        uint bySlotType,
        ushort byItemType,
        byte[] byDurability,
        byte byQuantity,
        byte wRefItemID,
        byte ullSerialNum,
        uint byOptLevel,
        ushort byExtra,
        uint dwPrice,
        uint wStackCount,
        ushort wField_13,
        uint dwField_14,
        uint dwField_15,
        byte byField_16,
        ulong ullField_17,
        uint dwField_18,
        byte[] bytesData_18,
        ulong ullField_20,
        uint dwField_21,
        byte byField_22,
        ulong ullField_23,
        byte byField_24,
        byte byField_25,
        byte byField_26,
        ulong ullField_27,
        ushort wField_28,
        uint dwField_29,
        ushort wField_30,
        byte byField_31,
        byte byField_32,
        uint dwField_33,
        uint dwField_34,
        byte byField_35,
        byte byField_36,
        uint dwField_37,
        uint dwField_38,
        uint dwField_39,
        byte byField_40,
        uint dwField_41,
        byte byField_42,
        ushort wField_43,
        ulong ullField_44,
        byte byField_45,
        byte byField_46,
        uint dwField_47,
        ushort wField_48
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyUpdate {
        pub by_action: u8,
        pub dw_stall_id: Vec<u8>,
        pub by_slot_type: u32,
        pub by_item_type: u16,
        pub by_durability: Vec<u8>,
        pub by_quantity: u8,
        pub w_ref_item_id: u8,
        pub ull_serial_num: u8,
        pub by_opt_level: u32,
        pub by_extra: u16,
        pub dw_price: u32,
        pub w_stack_count: u32,
        pub w_field_13: u16,
        pub dw_field_14: u32,
        pub dw_field_15: u32,
        pub by_field_16: u8,
        pub ull_field_17: u64,
        pub dw_field_18: u32,
        pub bytes_data_18: Vec<u8>,
        pub ull_field_20: u64,
        pub dw_field_21: u32,
        pub by_field_22: u8,
        pub ull_field_23: u64,
        pub by_field_24: u8,
        pub by_field_25: u8,
        pub by_field_26: u8,
        pub ull_field_27: u64,
        pub w_field_28: u16,
        pub dw_field_29: u32,
        pub w_field_30: u16,
        pub by_field_31: u8,
        pub by_field_32: u8,
        pub dw_field_33: u32,
        pub dw_field_34: u32,
        pub by_field_35: u8,
        pub by_field_36: u8,
        pub dw_field_37: u32,
        pub dw_field_38: u32,
        pub dw_field_39: u32,
        pub by_field_40: u8,
        pub dw_field_41: u32,
        pub by_field_42: u8,
        pub w_field_43: u16,
        pub ull_field_44: u64,
        pub by_field_45: u8,
        pub by_field_46: u8,
        pub dw_field_47: u32,
        pub w_field_48: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyUpdate struct {
        byAction uint8
        dwStallID []byte
        bySlotType uint32
        byItemType uint16
        byDurability []byte
        byQuantity uint8
        wRefItemID uint8
        ullSerialNum uint8
        byOptLevel uint32
        byExtra uint16
        dwPrice uint32
        wStackCount uint32
        wField_13 uint16
        dwField_14 uint32
        dwField_15 uint32
        byField_16 uint8
        ullField_17 uint64
        dwField_18 uint32
        bytesData_18 []byte
        ullField_20 uint64
        dwField_21 uint32
        byField_22 uint8
        ullField_23 uint64
        byField_24 uint8
        byField_25 uint8
        byField_26 uint8
        ullField_27 uint64
        wField_28 uint16
        dwField_29 uint32
        wField_30 uint16
        byField_31 uint8
        byField_32 uint8
        dwField_33 uint32
        dwField_34 uint32
        byField_35 uint8
        byField_36 uint8
        dwField_37 uint32
        dwField_38 uint32
        dwField_39 uint32
        byField_40 uint8
        dwField_41 uint32
        byField_42 uint8
        wField_43 uint16
        ullField_44 uint64
        byField_45 uint8
        byField_46 uint8
        dwField_47 uint32
        wField_48 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyUpdate {
        byAction: number;
        dwStallID: Uint8Array;
        bySlotType: number;
        byItemType: number;
        byDurability: Uint8Array;
        byQuantity: number;
        wRefItemID: number;
        ullSerialNum: number;
        byOptLevel: number;
        byExtra: number;
        dwPrice: number;
        wStackCount: number;
        wField_13: number;
        dwField_14: number;
        dwField_15: number;
        byField_16: number;
        ullField_17: bigint;
        dwField_18: number;
        bytesData_18: Uint8Array;
        ullField_20: bigint;
        dwField_21: number;
        byField_22: number;
        ullField_23: bigint;
        byField_24: number;
        byField_25: number;
        byField_26: number;
        ullField_27: bigint;
        wField_28: number;
        dwField_29: number;
        wField_30: number;
        byField_31: number;
        byField_32: number;
        dwField_33: number;
        dwField_34: number;
        byField_35: number;
        byField_36: number;
        dwField_37: number;
        dwField_38: number;
        dwField_39: number;
        byField_40: number;
        dwField_41: number;
        byField_42: number;
        wField_43: number;
        ullField_44: bigint;
        byField_45: number;
        byField_46: number;
        dwField_47: number;
        wField_48: number;
    }
    ```


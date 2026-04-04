# CLIENT_ENTITY_SPAWN_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB151` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x008729E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00872A2B` |
| 2 | `byAction` | `u8` | 1 | `0x00872A67` |
| 3 | `byParam` | `u8` | 1 | `0x00872A95` |
| 4 | `byItemSlot` | `u8` | 1 | `0x00872AA3` |
| 5 | `byOptResult` | `u32` | 4 | `0x008BB144` |
| 6 | `wRefItemID` | `u16` | 2 | `0x008BB174` |
| 7 | `dwField_07` | `u32` | 4 | `0x008BB192` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BB1A0` |
| 9 | `wField_09` | `u16` | 2 | `0x008BB1C4` |
| 10 | `dwField_10` | `u32` | 4 | `0x008BB1DE` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE549` |
| 12 | `byField_12` | `u8` | 1 | `0x008BE5DD` |
| 13 | `ullField_13` | `u64` | 8 | `0x008BE5ED` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BE5FB` |
| 15 | `bytesData_14` | `bytes` | variable | `0x008BE642` |
| 16 | `ullField_16` | `u64` | 8 | `0x008BE652` |
| 17 | `dwField_17` | `u32` | 4 | `0x008BE662` |
| 18 | `byField_18` | `u8` | 1 | `0x008BCE4B` |
| 19 | `ullField_19` | `u64` | 8 | `0x008BCE9F` |
| 20 | `byField_20` | `u8` | 1 | `0x008BB08E` |
| 21 | `byField_21` | `u8` | 1 | `0x008BB09C` |
| 22 | `byField_22` | `u8` | 1 | `0x008BB0BA` |
| 23 | `ullField_23` | `u64` | 8 | `0x008BB0C8` |
| 24 | `wField_24` | `u16` | 2 | `0x008BE6C9` |
| 25 | `wField_25` | `u16` | 2 | `0x004F7A7D` |
| 26 | `bytesData_25` | `bytes` | variable | `0x004F7AB9` |
| 27 | `dwField_27` | `u32` | 4 | `0x004F74CA` |
| 28 | `wField_28` | `u16` | 2 | `0x008BE75F` |
| 29 | `byField_29` | `u8` | 1 | `0x004F746A` |
| 30 | `byField_30` | `u8` | 1 | `0x008BE830` |
| 31 | `dwField_31` | `u32` | 4 | `0x008BE849` |
| 32 | `dwField_32` | `u32` | 4 | `0x008BE8F9` |
| 33 | `byField_33` | `u8` | 1 | `0x008BE927` |
| 34 | `byField_34` | `u8` | 1 | `0x008BE97D` |
| 35 | `dwField_35` | `u32` | 4 | `0x008BE98B` |
| 36 | `dwField_36` | `u32` | 4 | `0x008BE999` |
| 37 | `dwField_37` | `u32` | 4 | `0x008BE9DA` |
| 38 | `byField_38` | `u8` | 1 | `0x008BE9E8` |
| 39 | `dwField_39` | `u32` | 4 | `0x008BEAAE` |
| 40 | `byField_40` | `u8` | 1 | `0x00872B31` |
| 41 | `wField_41` | `u16` | 2 | `0x00872C7A` |

**Minimum size**: 115 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_ALCHEMY_CANCELED_COMPOUND` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] byParam                        u8
  [   3] byItemSlot                     u8
  [   4] byOptResult                    u32
  [   8] wRefItemID                     u16
  [  10] dwField_07                     u32
  [  14] dwField_08                     u32
  [  18] wField_09                      u16
  [  20] dwField_10                     u32
  [  24] dwField_11                     u32
  [  28] byField_12                     u8
  [  29] ullField_13                    u64
  [  37] dwField_14                     u32
  [  41] bytesData_14                   bytes  (variable length)
  [   0] ullField_16                    u64
  [   8] dwField_17                     u32
  [  12] byField_18                     u8
  [  13] ullField_19                    u64
  [  21] byField_20                     u8
  [  22] byField_21                     u8
  [  23] byField_22                     u8
  [  24] ullField_23                    u64
  [  32] wField_24                      u16
  [  34] wField_25                      u16
  [  36] bytesData_25                   bytes  (variable length)
  [   0] dwField_27                     u32
  [   4] wField_28                      u16
  [   6] byField_29                     u8
  [   7] byField_30                     u8
  [   8] dwField_31                     u32
  [  12] dwField_32                     u32
  [  16] byField_33                     u8
  [  17] byField_34                     u8
  [  18] dwField_35                     u32
  [  22] dwField_36                     u32
  [  26] dwField_37                     u32
  [  30] byField_38                     u8
  [  31] dwField_39                     u32
  [  35] byField_40                     u8
  [  36] wField_41                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpawnData {
        uint8_t byResult;
        uint8_t byAction;
        uint8_t byParam;
        uint8_t byItemSlot;
        uint32_t byOptResult;
        uint16_t wRefItemID;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint16_t wField_09;
        uint32_t dwField_10;
        uint32_t dwField_11;
        uint8_t byField_12;
        uint64_t ullField_13;
        uint32_t dwField_14;
        std::vector<uint8_t> bytesData_14;
        uint64_t ullField_16;
        uint32_t dwField_17;
        uint8_t byField_18;
        uint64_t ullField_19;
        uint8_t byField_20;
        uint8_t byField_21;
        uint8_t byField_22;
        uint64_t ullField_23;
        uint16_t wField_24;
        uint16_t wField_25;
        std::vector<uint8_t> bytesData_25;
        uint32_t dwField_27;
        uint16_t wField_28;
        uint8_t byField_29;
        uint8_t byField_30;
        uint32_t dwField_31;
        uint32_t dwField_32;
        uint8_t byField_33;
        uint8_t byField_34;
        uint32_t dwField_35;
        uint32_t dwField_36;
        uint32_t dwField_37;
        uint8_t byField_38;
        uint32_t dwField_39;
        uint8_t byField_40;
        uint16_t wField_41;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySpawnData(
        byte byResult,
        byte byAction,
        byte byParam,
        byte byItemSlot,
        uint byOptResult,
        ushort wRefItemID,
        uint dwField_07,
        uint dwField_08,
        ushort wField_09,
        uint dwField_10,
        uint dwField_11,
        byte byField_12,
        ulong ullField_13,
        uint dwField_14,
        byte[] bytesData_14,
        ulong ullField_16,
        uint dwField_17,
        byte byField_18,
        ulong ullField_19,
        byte byField_20,
        byte byField_21,
        byte byField_22,
        ulong ullField_23,
        ushort wField_24,
        ushort wField_25,
        byte[] bytesData_25,
        uint dwField_27,
        ushort wField_28,
        byte byField_29,
        byte byField_30,
        uint dwField_31,
        uint dwField_32,
        byte byField_33,
        byte byField_34,
        uint dwField_35,
        uint dwField_36,
        uint dwField_37,
        byte byField_38,
        uint dwField_39,
        byte byField_40,
        ushort wField_41
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpawnData {
        pub by_result: u8,
        pub by_action: u8,
        pub by_param: u8,
        pub by_item_slot: u8,
        pub by_opt_result: u32,
        pub w_ref_item_id: u16,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub w_field_09: u16,
        pub dw_field_10: u32,
        pub dw_field_11: u32,
        pub by_field_12: u8,
        pub ull_field_13: u64,
        pub dw_field_14: u32,
        pub bytes_data_14: Vec<u8>,
        pub ull_field_16: u64,
        pub dw_field_17: u32,
        pub by_field_18: u8,
        pub ull_field_19: u64,
        pub by_field_20: u8,
        pub by_field_21: u8,
        pub by_field_22: u8,
        pub ull_field_23: u64,
        pub w_field_24: u16,
        pub w_field_25: u16,
        pub bytes_data_25: Vec<u8>,
        pub dw_field_27: u32,
        pub w_field_28: u16,
        pub by_field_29: u8,
        pub by_field_30: u8,
        pub dw_field_31: u32,
        pub dw_field_32: u32,
        pub by_field_33: u8,
        pub by_field_34: u8,
        pub dw_field_35: u32,
        pub dw_field_36: u32,
        pub dw_field_37: u32,
        pub by_field_38: u8,
        pub dw_field_39: u32,
        pub by_field_40: u8,
        pub w_field_41: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpawnData struct {
        byResult uint8
        byAction uint8
        byParam uint8
        byItemSlot uint8
        byOptResult uint32
        wRefItemID uint16
        dwField_07 uint32
        dwField_08 uint32
        wField_09 uint16
        dwField_10 uint32
        dwField_11 uint32
        byField_12 uint8
        ullField_13 uint64
        dwField_14 uint32
        bytesData_14 []byte
        ullField_16 uint64
        dwField_17 uint32
        byField_18 uint8
        ullField_19 uint64
        byField_20 uint8
        byField_21 uint8
        byField_22 uint8
        ullField_23 uint64
        wField_24 uint16
        wField_25 uint16
        bytesData_25 []byte
        dwField_27 uint32
        wField_28 uint16
        byField_29 uint8
        byField_30 uint8
        dwField_31 uint32
        dwField_32 uint32
        byField_33 uint8
        byField_34 uint8
        dwField_35 uint32
        dwField_36 uint32
        dwField_37 uint32
        byField_38 uint8
        dwField_39 uint32
        byField_40 uint8
        wField_41 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySpawnData {
        byResult: number;
        byAction: number;
        byParam: number;
        byItemSlot: number;
        byOptResult: number;
        wRefItemID: number;
        dwField_07: number;
        dwField_08: number;
        wField_09: number;
        dwField_10: number;
        dwField_11: number;
        byField_12: number;
        ullField_13: bigint;
        dwField_14: number;
        bytesData_14: Uint8Array;
        ullField_16: bigint;
        dwField_17: number;
        byField_18: number;
        ullField_19: bigint;
        byField_20: number;
        byField_21: number;
        byField_22: number;
        ullField_23: bigint;
        wField_24: number;
        wField_25: number;
        bytesData_25: Uint8Array;
        dwField_27: number;
        wField_28: number;
        byField_29: number;
        byField_30: number;
        dwField_31: number;
        dwField_32: number;
        byField_33: number;
        byField_34: number;
        dwField_35: number;
        dwField_36: number;
        dwField_37: number;
        byField_38: number;
        dwField_39: number;
        byField_40: number;
        wField_41: number;
    }
    ```


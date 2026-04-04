# SERVER_STALL_TALK_RESPONSE

> Previously documented as `CLIENT_PARTY_DATA` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB0B3` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087A260` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `ullField_10` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `unk` | `u32` | 4 | if(packet.ReadBool() |
| 3 | `note` | `string` | var | if(packet.ReadBool() |
| 4 | `isOpen` | `bool` | 1 | if(packet.ReadBool() |
| 5 | `mode` | `u8` | 1 | if(packet.ReadBool() |
| 6 | `slotStall` | `u8` | 1 | if(packet.ReadBool() |
| 7 | `SlotInventory` | `u8` | 1 | if(packet.ReadBool() |
| 8 | `Quantity` | `u16` | 2 | if(packet.ReadBool() |
| 9 | `Price` | `u64` | 8 | if(packet.ReadBool() |
| 10 | `unk` | `u8` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087A2B3` |
| 2 | `dwStallID` | `u32` | 4 | `0x0087A2FD` |
| 3 | `dwParam1` | `u32` | 4 | `0x0087A32A` |
| 4 | `byExtra` | `u8` | 1 | `0x0087A387` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x00872337` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BE549` |
| 9 | `byField_09` | `u8` | 1 | `0x008BE5DD` |
| 10 | `ullField_10` | `u64` | 8 | `0x008BE5ED` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE5FB` |
| 12 | `bytesData_11` | `bytes` | variable | `0x008BE642` |
| 13 | `ullField_13` | `u64` | 8 | `0x008BE652` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BE662` |
| 15 | `wField_15` | `u16` | 2 | `0x008BE6C9` |
| 16 | `wField_16` | `u16` | 2 | `0x008BE75F` |
| 17 | `byField_17` | `u8` | 1 | `0x008BE830` |
| 18 | `dwField_18` | `u32` | 4 | `0x008BE849` |
| 19 | `dwField_19` | `u32` | 4 | `0x008BE8F9` |
| 20 | `byField_20` | `u8` | 1 | `0x008BE927` |
| 21 | `byField_21` | `u8` | 1 | `0x008BE97D` |
| 22 | `dwField_22` | `u32` | 4 | `0x008BE98B` |
| 23 | `dwField_23` | `u32` | 4 | `0x008BE999` |
| 24 | `dwField_24` | `u32` | 4 | `0x008BE9DA` |
| 25 | `byField_25` | `u8` | 1 | `0x008BE9E8` |
| 26 | `dwField_26` | `u32` | 4 | `0x008BEAAE` |
| 27 | `byField_27` | `u8` | 1 | `0x00872370` |
| 28 | `wField_28` | `u16` | 2 | `0x00872389` |
| 29 | `ullField_29` | `u64` | 8 | `0x0087239A` |
| 30 | `byField_30` | `u8` | 1 | `0x008723FD` |
| 31 | `bytesData_30` | `bytes` | variable | `0x00841948` |

**Minimum size**: 86 bytes + variable fields

</details>
### String References
| String | Type |
|--------|------|
| `UIIT_MSG_WARENETWORK_BUY_SUCCESS` | UI |
| `UIIT_MSG_WARENETWORK_CHARGE` | UI |
| `UIIT_MSG_STREET_STORE_SELL_COMMODITY` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwStallID                      u32
  [   5] dwParam1                       u32
  [   9] byExtra                        u8
  [  10] wField_05                      u16
  [  12] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] byField_09                     u8
  [   6] ullField_10                    u64
  [  14] dwField_11                     u32
  [  18] bytesData_11                   bytes  (variable length)
  [   0] ullField_13                    u64
  [   8] dwField_14                     u32
  [  12] wField_15                      u16
  [  14] wField_16                      u16
  [  16] byField_17                     u8
  [  17] dwField_18                     u32
  [  21] dwField_19                     u32
  [  25] byField_20                     u8
  [  26] byField_21                     u8
  [  27] dwField_22                     u32
  [  31] dwField_23                     u32
  [  35] dwField_24                     u32
  [  39] byField_25                     u8
  [  40] dwField_26                     u32
  [  44] byField_27                     u8
  [  45] wField_28                      u16
  [  47] ullField_29                    u64
  [  55] byField_30                     u8
  [  56] bytesData_30                   bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyData {
        uint8_t byAction;
        uint32_t dwStallID;
        uint32_t dwParam1;
        uint8_t byExtra;
        uint16_t wField_05;
        std::vector<uint8_t> bytesData_5;
        uint8_t byField_07;
        uint32_t dwField_08;
        uint8_t byField_09;
        uint64_t ullField_10;
        uint32_t dwField_11;
        std::vector<uint8_t> bytesData_11;
        uint64_t ullField_13;
        uint32_t dwField_14;
        uint16_t wField_15;
        uint16_t wField_16;
        uint8_t byField_17;
        uint32_t dwField_18;
        uint32_t dwField_19;
        uint8_t byField_20;
        uint8_t byField_21;
        uint32_t dwField_22;
        uint32_t dwField_23;
        uint32_t dwField_24;
        uint8_t byField_25;
        uint32_t dwField_26;
        uint8_t byField_27;
        uint16_t wField_28;
        uint64_t ullField_29;
        uint8_t byField_30;
        std::vector<uint8_t> bytesData_30;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyData(
        byte byAction,
        uint dwStallID,
        uint dwParam1,
        byte byExtra,
        ushort wField_05,
        byte[] bytesData_5,
        byte byField_07,
        uint dwField_08,
        byte byField_09,
        ulong ullField_10,
        uint dwField_11,
        byte[] bytesData_11,
        ulong ullField_13,
        uint dwField_14,
        ushort wField_15,
        ushort wField_16,
        byte byField_17,
        uint dwField_18,
        uint dwField_19,
        byte byField_20,
        byte byField_21,
        uint dwField_22,
        uint dwField_23,
        uint dwField_24,
        byte byField_25,
        uint dwField_26,
        byte byField_27,
        ushort wField_28,
        ulong ullField_29,
        byte byField_30,
        byte[] bytesData_30
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyData {
        pub by_action: u8,
        pub dw_stall_id: u32,
        pub dw_param1: u32,
        pub by_extra: u8,
        pub w_field_05: u16,
        pub bytes_data_5: Vec<u8>,
        pub by_field_07: u8,
        pub dw_field_08: u32,
        pub by_field_09: u8,
        pub ull_field_10: u64,
        pub dw_field_11: u32,
        pub bytes_data_11: Vec<u8>,
        pub ull_field_13: u64,
        pub dw_field_14: u32,
        pub w_field_15: u16,
        pub w_field_16: u16,
        pub by_field_17: u8,
        pub dw_field_18: u32,
        pub dw_field_19: u32,
        pub by_field_20: u8,
        pub by_field_21: u8,
        pub dw_field_22: u32,
        pub dw_field_23: u32,
        pub dw_field_24: u32,
        pub by_field_25: u8,
        pub dw_field_26: u32,
        pub by_field_27: u8,
        pub w_field_28: u16,
        pub ull_field_29: u64,
        pub by_field_30: u8,
        pub bytes_data_30: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyData struct {
        byAction uint8
        dwStallID uint32
        dwParam1 uint32
        byExtra uint8
        wField_05 uint16
        bytesData_5 []byte
        byField_07 uint8
        dwField_08 uint32
        byField_09 uint8
        ullField_10 uint64
        dwField_11 uint32
        bytesData_11 []byte
        ullField_13 uint64
        dwField_14 uint32
        wField_15 uint16
        wField_16 uint16
        byField_17 uint8
        dwField_18 uint32
        dwField_19 uint32
        byField_20 uint8
        byField_21 uint8
        dwField_22 uint32
        dwField_23 uint32
        dwField_24 uint32
        byField_25 uint8
        dwField_26 uint32
        byField_27 uint8
        wField_28 uint16
        ullField_29 uint64
        byField_30 uint8
        bytesData_30 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyData {
        byAction: number;
        dwStallID: number;
        dwParam1: number;
        byExtra: number;
        wField_05: number;
        bytesData_5: Uint8Array;
        byField_07: number;
        dwField_08: number;
        byField_09: number;
        ullField_10: bigint;
        dwField_11: number;
        bytesData_11: Uint8Array;
        ullField_13: bigint;
        dwField_14: number;
        wField_15: number;
        wField_16: number;
        byField_17: number;
        dwField_18: number;
        dwField_19: number;
        byField_20: number;
        byField_21: number;
        dwField_22: number;
        dwField_23: number;
        dwField_24: number;
        byField_25: number;
        dwField_26: number;
        byField_27: number;
        wField_28: number;
        ullField_29: bigint;
        byField_30: number;
        bytesData_30: Uint8Array;
    }
    ```


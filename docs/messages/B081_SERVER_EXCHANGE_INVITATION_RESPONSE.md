# SERVER_EXCHANGE_INVITATION_RESPONSE

> Previously documented as `CLIENT_INVENTORY_REQUEST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB081` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008847D0`, `0x0088AA60` |

## Handler 1: `0x008847D0`

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byAction` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `uniqueID` | `u32` | 4 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00884801` |
| 2 | `wSlot1` | `u16` | 2 | `0x0088481D` |
| 3 | `wSlot2` | `u16` | 2 | `0x00884919` |

**Total size**: 5 bytes

</details>
### String References
| String | Type |
|--------|------|
| `UIIT_MSG_PARTYMATCH_JOIN_COMPLETE_MASTER` | UI |
| `UIIT_MSG_PARTYERR_CREATE_PARTY_REFUSED` | UI |
| `UIIT_MSG_PARTYMATCH_JOIN_NOREPLY` | UI |
| `UIIT_MSG_PARTYMATCH_AUTO_FAILURE` | UI |
| `UIIT_MSG_PARTYMATCH_AUTO_PROGRESS` | UI |

### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `simple_msgbox_type` | Debug |
| `UIIT_STT_CONFIRM_BOX` | UI |
| `UIIT_MSG_QUEST_ENTER_INSTANCE` | UI |
| `UIIT_MSG_MSGBOX_ASK_REBIRTH_MUTATION` | UI |
| `UIIT_PAG_PARTYMATCH_JOINREQUEST` | UI |
| `UIIT_STT_TC_JOIN_REQUEST` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wSlot1                         u16
  [   3] wSlot2                         u16
```

## Handler 2: `0x0088AA60`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0088AAAF` |
| 2 | `wSlot1` | `u32` | 4 | `0x0088AABD` |
| 3 | `wSlot2` | `bytes` | variable | `0x00841948` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byField_06` | `u8` | 1 | `0x0088AD93` |
| 7 | `byField_07` | `u8` | 1 | `0x008859A6` |
| 8 | `dwField_08` | `u32` | 4 | `0x008859B4` |
| 9 | `byField_09` | `u8` | 1 | `0x008859C2` |
| 10 | `dwField_10` | `u32` | 4 | `0x008859D0` |
| 11 | `dwField_11` | `u32` | 4 | `0x00889CCE` |
| 12 | `byField_12` | `u8` | 1 | `0x00889CDB` |
| 13 | `dwField_13` | `u32` | 4 | `0x00889CE8` |
| 14 | `byField_14` | `u8` | 1 | `0x00889CF5` |
| 15 | `byField_15` | `u8` | 1 | `0x00889D02` |
| 16 | `dwField_16` | `u32` | 4 | `0x00889D0F` |
| 17 | `dwField_17` | `u32` | 4 | `0x00889D1C` |
| 18 | `wField_18` | `u16` | 2 | `0x00889D2A` |
| 19 | `dwField_19` | `u32` | 4 | `0x00889D6F` |

**Minimum size**: 43 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_PARTYMATCH_JOIN_COMPLETE_MASTER` | UI |
| `UIIT_MSG_PARTYERR_CREATE_PARTY_REFUSED` | UI |
| `UIIT_MSG_PARTYMATCH_JOIN_NOREPLY` | UI |
| `UIIT_MSG_PARTYMATCH_AUTO_FAILURE` | UI |
| `UIIT_MSG_PARTYMATCH_AUTO_PROGRESS` | UI |

### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `simple_msgbox_type` | Debug |
| `UIIT_STT_CONFIRM_BOX` | UI |
| `UIIT_MSG_QUEST_ENTER_INSTANCE` | UI |
| `UIIT_MSG_MSGBOX_ASK_REBIRTH_MUTATION` | UI |
| `UIIT_PAG_PARTYMATCH_JOINREQUEST` | UI |
| `UIIT_STT_TC_JOIN_REQUEST` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wSlot1                         u32
  [   5] wSlot2                         bytes  (variable length)
  [   0] wField_04                      u16
  [   2] bytesData_4                    bytes  (variable length)
  [   0] byField_06                     u8
  [   1] byField_07                     u8
  [   2] dwField_08                     u32
  [   6] byField_09                     u8
  [   7] dwField_10                     u32
  [  11] dwField_11                     u32
  [  15] byField_12                     u8
  [  16] dwField_13                     u32
  [  20] byField_14                     u8
  [  21] byField_15                     u8
  [  22] dwField_16                     u32
  [  26] dwField_17                     u32
  [  30] wField_18                      u16
  [  32] dwField_19                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryRequest {
        uint8_t byAction;
        uint16_t wSlot1;
        uint16_t wSlot2;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
        uint8_t byField_06;
        uint8_t byField_07;
        uint32_t dwField_08;
        uint8_t byField_09;
        uint32_t dwField_10;
        uint32_t dwField_11;
        uint8_t byField_12;
        uint32_t dwField_13;
        uint8_t byField_14;
        uint8_t byField_15;
        uint32_t dwField_16;
        uint32_t dwField_17;
        uint16_t wField_18;
        uint32_t dwField_19;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryRequest(
        byte byAction,
        ushort wSlot1,
        ushort wSlot2,
        ushort wField_04,
        byte[] bytesData_4,
        byte byField_06,
        byte byField_07,
        uint dwField_08,
        byte byField_09,
        uint dwField_10,
        uint dwField_11,
        byte byField_12,
        uint dwField_13,
        byte byField_14,
        byte byField_15,
        uint dwField_16,
        uint dwField_17,
        ushort wField_18,
        uint dwField_19
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryRequest {
        pub by_action: u8,
        pub w_slot1: u16,
        pub w_slot2: u16,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
        pub by_field_06: u8,
        pub by_field_07: u8,
        pub dw_field_08: u32,
        pub by_field_09: u8,
        pub dw_field_10: u32,
        pub dw_field_11: u32,
        pub by_field_12: u8,
        pub dw_field_13: u32,
        pub by_field_14: u8,
        pub by_field_15: u8,
        pub dw_field_16: u32,
        pub dw_field_17: u32,
        pub w_field_18: u16,
        pub dw_field_19: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryRequest struct {
        byAction uint8
        wSlot1 uint16
        wSlot2 uint16
        wField_04 uint16
        bytesData_4 []byte
        byField_06 uint8
        byField_07 uint8
        dwField_08 uint32
        byField_09 uint8
        dwField_10 uint32
        dwField_11 uint32
        byField_12 uint8
        dwField_13 uint32
        byField_14 uint8
        byField_15 uint8
        dwField_16 uint32
        dwField_17 uint32
        wField_18 uint16
        dwField_19 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryRequest {
        byAction: number;
        wSlot1: number;
        wSlot2: number;
        wField_04: number;
        bytesData_4: Uint8Array;
        byField_06: number;
        byField_07: number;
        dwField_08: number;
        byField_09: number;
        dwField_10: number;
        dwField_11: number;
        byField_12: number;
        dwField_13: number;
        byField_14: number;
        byField_15: number;
        dwField_16: number;
        dwField_17: number;
        wField_18: number;
        dwField_19: number;
    }
    ```


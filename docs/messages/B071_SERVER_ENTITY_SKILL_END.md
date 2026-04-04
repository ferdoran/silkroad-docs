# SERVER_ENTITY_SKILL_END

> **Corrected name** (server RE): Was `CLIENT_ENTITY_DETAIL_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB071` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A5FD0` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Success` | `bool` | 1 | Whether the skill ended successfully |

If `Success`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `SkillUniqueID` | `u32` | 4 | Unique instance ID of the ending skill |
| 3 | `TargetUniqueID` | `u32` | 4 | Target entity |

Followed by [DamageData](B070_SERVER_ENTITY_SKILL_START.md#damagedata-shared-sub-structure) (same sub-structure as SKILL_START).

### Structure Summary

```
  [   0] Success                        bool
  if Success:
    [   1] SkillUniqueID                u32
    [   5] TargetUniqueID               u32
    [   9] DamageData                   (variable)
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A600B` |
| 2 | `wParam` | `u16` | 2 | `0x008A6020` |
| 3 | `byAction` | `bytes` | variable | `0x008A6052` |
| 4 | `dwUniqueID1` | `u32` | 4 | `0x008A6060` |
| 5 | `dwUniqueID2` | `u32` | 4 | `0x008A606E` |
| 6 | `dwTargetUID` | `u32` | 4 | `0x008A607C` |
| 7 | `dwField_07` | `u32` | 4 | `0x00A54C5D` |
| 8 | `byField_08` | `u8` | 1 | `0x00A54C7F` |
| 9 | `byField_09` | `u8` | 1 | `0x00A548F6` |
| 10 | `byField_10` | `u8` | 1 | `0x00A54904` |
| 11 | `dwField_11` | `u32` | 4 | `0x00A54CBB` |
| 12 | `wField_12` | `u16` | 2 | `0x00A54D1F` |
| 13 | `bytesData_12` | `bytes[12]` | 12 | `0x00A54D2D` |
| 14 | `bytesData_13` | `bytes` | variable | `0x00A54E02` |
| 15 | `bytesData_14` | `bytes[12]` | 12 | `0x00A54E10` |
| 16 | `bytesData_15` | `bytes` | variable | `0x008416B1` |
| 17 | `bytesData_16` | `bytes` | variable | `0x00841948` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySkillEnd {
        bool Success;
        uint32_t SkillUniqueID;
        uint32_t TargetUniqueID;
        uint8_t byResult;
        uint16_t wParam;
        std::vector<uint8_t> byAction;
        uint32_t dwUniqueID1;
        uint32_t dwUniqueID2;
        uint32_t dwTargetUID;
        uint32_t dwField_07;
        uint8_t byField_08;
        uint8_t byField_09;
        uint8_t byField_10;
        uint32_t dwField_11;
        uint16_t wField_12;
        uint8_t bytesData_12;
        std::vector<uint8_t> bytesData_13;
        uint8_t bytesData_14;
        std::vector<uint8_t> bytesData_15;
        std::vector<uint8_t> bytesData_16;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySkillEnd(
        bool Success,
        uint SkillUniqueID,
        uint TargetUniqueID,
        byte byResult,
        ushort wParam,
        byte[] byAction,
        uint dwUniqueID1,
        uint dwUniqueID2,
        uint dwTargetUID,
        uint dwField_07,
        byte byField_08,
        byte byField_09,
        byte byField_10,
        uint dwField_11,
        ushort wField_12,
        byte bytesData_12,
        byte[] bytesData_13,
        byte bytesData_14,
        byte[] bytesData_15,
        byte[] bytesData_16
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySkillEnd {
        pub success: bool,
        pub skill_unique_id: u32,
        pub target_unique_id: u32,
        pub by_result: u8,
        pub w_param: u16,
        pub by_action: Vec<u8>,
        pub dw_unique_id1: u32,
        pub dw_unique_id2: u32,
        pub dw_target_uid: u32,
        pub dw_field_07: u32,
        pub by_field_08: u8,
        pub by_field_09: u8,
        pub by_field_10: u8,
        pub dw_field_11: u32,
        pub w_field_12: u16,
        pub bytes_data_12: u8,
        pub bytes_data_13: Vec<u8>,
        pub bytes_data_14: u8,
        pub bytes_data_15: Vec<u8>,
        pub bytes_data_16: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySkillEnd struct {
        Success bool
        SkillUniqueID uint32
        TargetUniqueID uint32
        byResult uint8
        wParam uint16
        byAction []byte
        dwUniqueID1 uint32
        dwUniqueID2 uint32
        dwTargetUID uint32
        dwField_07 uint32
        byField_08 uint8
        byField_09 uint8
        byField_10 uint8
        dwField_11 uint32
        wField_12 uint16
        bytesData_12 uint8
        bytesData_13 []byte
        bytesData_14 uint8
        bytesData_15 []byte
        bytesData_16 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySkillEnd {
        success: boolean;
        skillUniqueID: number;
        targetUniqueID: number;
        byResult: number;
        wParam: number;
        byAction: Uint8Array;
        dwUniqueID1: number;
        dwUniqueID2: number;
        dwTargetUID: number;
        dwField_07: number;
        byField_08: number;
        byField_09: number;
        byField_10: number;
        dwField_11: number;
        wField_12: number;
        bytesData_12: number;
        bytesData_13: Uint8Array;
        bytesData_14: number;
        bytesData_15: Uint8Array;
        bytesData_16: Uint8Array;
    }
    ```


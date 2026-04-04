# CLIENT_PARTY_MATCH_JOIN_REQUEST

> **Corrected name** (server RE): Was `SERVER_SOCIAL_DATA` (client-derived). Direction: Client→Server (0x7xxx). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x706D` |
| Direction | Client → Server |
| Group | Chat/Social |
| Handler(s) | `0x008841F0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `requestID` | `u32` | 4 |  |
| 2 | `joinID` | `u32` | 4 |  |
| 3 | `matchNumber` | `u32` | 4 |  |
| 4 | `masteryID_primary` | `u32` | 4 |  |
| 5 | `masteryID_secondary` | `u32` | 4 |  |
| 6 | `unkByte00` | `u8` | 1 |  |
| 7 | `unkByte01` | `u8` | 1 |  |
| 8 | `joinID_x2` | `u32` | 4 |  |
| 9 | `name` | `string` | var |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088423B` |
| 2 | `byField_02` | `u8` | 1 | `0x00884255` |
| 3 | `byField_03` | `u8` | 1 | `0x00884263` |
| 4 | `byField_04` | `u8` | 1 | `0x00884271` |
| 5 | `dwField_05` | `u32` | 4 | `0x00884392` |
| 6 | `dwField_06` | `u32` | 4 | `0x008843A0` |
| 7 | `wField_07` | `u16` | 2 | `0x004F7A7D` |
| 8 | `bytesData_7` | `bytes` | variable | `0x004F7AB9` |
| 9 | `byField_09` | `u8` | 1 | `0x008843BF` |
| 10 | `byField_10` | `u8` | 1 | `0x008843CD` |
| 11 | `byField_11` | `u8` | 1 | `0x008843DB` |
| 12 | `byField_12` | `u8` | 1 | `0x008843E9` |
| 13 | `byField_13` | `u8` | 1 | `0x008843F7` |
| 14 | `byField_14` | `u8` | 1 | `0x00884405` |
| 15 | `wField_15` | `u16` | 2 | `0x0088460D` |

**Minimum size**: 22 bytes + variable fields

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] wField_07                      u16
  [  14] bytesData_7                    bytes  (variable length)
  [   0] byField_09                     u8
  [   1] byField_10                     u8
  [   2] byField_11                     u8
  [   3] byField_12                     u8
  [   4] byField_13                     u8
  [   5] byField_14                     u8
  [   6] wField_15                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyMatchJoinRequest {
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint16_t wField_07;
        std::vector<uint8_t> bytesData_7;
        uint8_t byField_09;
        uint8_t byField_10;
        uint8_t byField_11;
        uint8_t byField_12;
        uint8_t byField_13;
        uint8_t byField_14;
        uint16_t wField_15;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyMatchJoinRequest(
        byte byResult,
        byte byField_02,
        byte byField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06,
        ushort wField_07,
        byte[] bytesData_7,
        byte byField_09,
        byte byField_10,
        byte byField_11,
        byte byField_12,
        byte byField_13,
        byte byField_14,
        ushort wField_15
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyMatchJoinRequest {
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub w_field_07: u16,
        pub bytes_data_7: Vec<u8>,
        pub by_field_09: u8,
        pub by_field_10: u8,
        pub by_field_11: u8,
        pub by_field_12: u8,
        pub by_field_13: u8,
        pub by_field_14: u8,
        pub w_field_15: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyMatchJoinRequest struct {
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
        wField_07 uint16
        bytesData_7 []byte
        byField_09 uint8
        byField_10 uint8
        byField_11 uint8
        byField_12 uint8
        byField_13 uint8
        byField_14 uint8
        wField_15 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyMatchJoinRequest {
        byResult: number;
        byField_02: number;
        byField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
        wField_07: number;
        bytesData_7: Uint8Array;
        byField_09: number;
        byField_10: number;
        byField_11: number;
        byField_12: number;
        byField_13: number;
        byField_14: number;
        wField_15: number;
    }
    ```


# SERVER_ACADEMY_DATA

> Previously documented as `SERVER_STALL_UPDATE_DATA` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3C81` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x00899630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089963E` |
| 2 | `dwField_02` | `u32` | 4 | `0x0099AD49` |
| 3 | `bytesData_2` | `bytes[16]` | 16 | `0x0099AD57` |
| 4 | `byField_04` | `u8` | 1 | `0x0099AD65` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x009995DF` |
| 8 | `dwField_08` | `u32` | 4 | `0x00999621` |
| 9 | `dwField_09` | `u32` | 4 | `0x0099962F` |
| 10 | `dwField_10` | `u32` | 4 | `0x0099963D` |
| 11 | `wField_11` | `u16` | 2 | `0x0099964B` |
| 12 | `bytesData_11` | `bytes` | variable | `0x009996A4` |
| 13 | `byField_13` | `u8` | 1 | `0x009996B2` |
| 14 | `byField_14` | `u8` | 1 | `0x009996C0` |
| 15 | `bytesData_14` | `bytes` | variable | `0x009996CD` |
| 16 | `byField_16` | `u8` | 1 | `0x009996DB` |
| 17 | `byField_17` | `u8` | 1 | `0x009996E9` |
| 18 | `dwField_18` | `u32` | 4 | `0x009996F7` |
| 19 | `byField_19` | `u8` | 1 | `0x00999705` |
| 20 | `dwField_20` | `u32` | 4 | `0x00999713` |
| 21 | `wField_21` | `u16` | 2 | `0x00999721` |
| 22 | `wField_22` | `u16` | 2 | `0x0099972F` |
| 23 | `wField_23` | `u16` | 2 | `0x0099973D` |
| 24 | `wField_24` | `u16` | 2 | `0x0099974B` |
| 25 | `wField_25` | `u16` | 2 | `0x00999759` |
| 26 | `bytesData_25` | `bytes` | variable | `0x009997AD` |

**Minimum size**: 62 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_TC_OPEN_SUCCESS` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] bytesData_2                    bytes[16]
  [  21] byField_04                     u8
  [  22] wField_05                      u16
  [  24] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] dwField_09                     u32
  [   9] dwField_10                     u32
  [  13] wField_11                      u16
  [  15] bytesData_11                   bytes  (variable length)
  [   0] byField_13                     u8
  [   1] byField_14                     u8
  [   2] bytesData_14                   bytes  (variable length)
  [   0] byField_16                     u8
  [   1] byField_17                     u8
  [   2] dwField_18                     u32
  [   6] byField_19                     u8
  [   7] dwField_20                     u32
  [  11] wField_21                      u16
  [  13] wField_22                      u16
  [  15] wField_23                      u16
  [  17] wField_24                      u16
  [  19] wField_25                      u16
  [  21] bytesData_25                   bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallUpdateData {
        uint8_t byResult;
        uint32_t dwField_02;
        uint8_t bytesData_2;
        uint8_t byField_04;
        uint16_t wField_05;
        std::vector<uint8_t> bytesData_5;
        uint8_t byField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint32_t dwField_10;
        uint16_t wField_11;
        std::vector<uint8_t> bytesData_11;
        uint8_t byField_13;
        uint8_t byField_14;
        std::vector<uint8_t> bytesData_14;
        uint8_t byField_16;
        uint8_t byField_17;
        uint32_t dwField_18;
        uint8_t byField_19;
        uint32_t dwField_20;
        uint16_t wField_21;
        uint16_t wField_22;
        uint16_t wField_23;
        uint16_t wField_24;
        uint16_t wField_25;
        std::vector<uint8_t> bytesData_25;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallUpdateData(
        byte byResult,
        uint dwField_02,
        byte bytesData_2,
        byte byField_04,
        ushort wField_05,
        byte[] bytesData_5,
        byte byField_07,
        uint dwField_08,
        uint dwField_09,
        uint dwField_10,
        ushort wField_11,
        byte[] bytesData_11,
        byte byField_13,
        byte byField_14,
        byte[] bytesData_14,
        byte byField_16,
        byte byField_17,
        uint dwField_18,
        byte byField_19,
        uint dwField_20,
        ushort wField_21,
        ushort wField_22,
        ushort wField_23,
        ushort wField_24,
        ushort wField_25,
        byte[] bytesData_25
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallUpdateData {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub bytes_data_2: u8,
        pub by_field_04: u8,
        pub w_field_05: u16,
        pub bytes_data_5: Vec<u8>,
        pub by_field_07: u8,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub dw_field_10: u32,
        pub w_field_11: u16,
        pub bytes_data_11: Vec<u8>,
        pub by_field_13: u8,
        pub by_field_14: u8,
        pub bytes_data_14: Vec<u8>,
        pub by_field_16: u8,
        pub by_field_17: u8,
        pub dw_field_18: u32,
        pub by_field_19: u8,
        pub dw_field_20: u32,
        pub w_field_21: u16,
        pub w_field_22: u16,
        pub w_field_23: u16,
        pub w_field_24: u16,
        pub w_field_25: u16,
        pub bytes_data_25: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallUpdateData struct {
        byResult uint8
        dwField_02 uint32
        bytesData_2 uint8
        byField_04 uint8
        wField_05 uint16
        bytesData_5 []byte
        byField_07 uint8
        dwField_08 uint32
        dwField_09 uint32
        dwField_10 uint32
        wField_11 uint16
        bytesData_11 []byte
        byField_13 uint8
        byField_14 uint8
        bytesData_14 []byte
        byField_16 uint8
        byField_17 uint8
        dwField_18 uint32
        byField_19 uint8
        dwField_20 uint32
        wField_21 uint16
        wField_22 uint16
        wField_23 uint16
        wField_24 uint16
        wField_25 uint16
        bytesData_25 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallUpdateData {
        byResult: number;
        dwField_02: number;
        bytesData_2: number;
        byField_04: number;
        wField_05: number;
        bytesData_5: Uint8Array;
        byField_07: number;
        dwField_08: number;
        dwField_09: number;
        dwField_10: number;
        wField_11: number;
        bytesData_11: Uint8Array;
        byField_13: number;
        byField_14: number;
        bytesData_14: Uint8Array;
        byField_16: number;
        byField_17: number;
        dwField_18: number;
        byField_19: number;
        dwField_20: number;
        wField_21: number;
        wField_22: number;
        wField_23: number;
        wField_24: number;
        wField_25: number;
        bytesData_25: Uint8Array;
    }
    ```


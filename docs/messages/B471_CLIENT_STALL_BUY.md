# CLIENT_STALL_BUY
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB471` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x008986C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0099AD49` |
| 2 | `bytesData_1` | `bytes[16]` | 16 | `0x0099AD57` |
| 3 | `byField_03` | `u8` | 1 | `0x0099AD65` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byField_06` | `u8` | 1 | `0x009995DF` |
| 7 | `dwField_07` | `u32` | 4 | `0x00999621` |
| 8 | `dwField_08` | `u32` | 4 | `0x0099962F` |
| 9 | `dwField_09` | `u32` | 4 | `0x0099963D` |
| 10 | `wField_10` | `u16` | 2 | `0x0099964B` |
| 11 | `bytesData_10` | `bytes` | variable | `0x009996A4` |
| 12 | `byField_12` | `u8` | 1 | `0x009996B2` |
| 13 | `byField_13` | `u8` | 1 | `0x009996C0` |
| 14 | `bytesData_13` | `bytes` | variable | `0x009996CD` |
| 15 | `byField_15` | `u8` | 1 | `0x009996DB` |
| 16 | `byField_16` | `u8` | 1 | `0x009996E9` |
| 17 | `dwField_17` | `u32` | 4 | `0x009996F7` |
| 18 | `byField_18` | `u8` | 1 | `0x00999705` |
| 19 | `dwField_19` | `u32` | 4 | `0x00999713` |
| 20 | `wField_20` | `u16` | 2 | `0x00999721` |
| 21 | `wField_21` | `u16` | 2 | `0x0099972F` |
| 22 | `wField_22` | `u16` | 2 | `0x0099973D` |
| 23 | `wField_23` | `u16` | 2 | `0x0099974B` |
| 24 | `wField_24` | `u16` | 2 | `0x00999759` |
| 25 | `bytesData_24` | `bytes` | variable | `0x009997AD` |

**Minimum size**: 61 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] bytesData_1                    bytes[16]
  [  20] byField_03                     u8
  [  21] wField_04                      u16
  [  23] bytesData_4                    bytes  (variable length)
  [   0] byField_06                     u8
  [   1] dwField_07                     u32
  [   5] dwField_08                     u32
  [   9] dwField_09                     u32
  [  13] wField_10                      u16
  [  15] bytesData_10                   bytes  (variable length)
  [   0] byField_12                     u8
  [   1] byField_13                     u8
  [   2] bytesData_13                   bytes  (variable length)
  [   0] byField_15                     u8
  [   1] byField_16                     u8
  [   2] dwField_17                     u32
  [   6] byField_18                     u8
  [   7] dwField_19                     u32
  [  11] wField_20                      u16
  [  13] wField_21                      u16
  [  15] wField_22                      u16
  [  17] wField_23                      u16
  [  19] wField_24                      u16
  [  21] bytesData_24                   bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallBuy {
        uint32_t dwUniqueID;
        uint8_t bytesData_1;
        uint8_t byField_03;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
        uint8_t byField_06;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint16_t wField_10;
        std::vector<uint8_t> bytesData_10;
        uint8_t byField_12;
        uint8_t byField_13;
        std::vector<uint8_t> bytesData_13;
        uint8_t byField_15;
        uint8_t byField_16;
        uint32_t dwField_17;
        uint8_t byField_18;
        uint32_t dwField_19;
        uint16_t wField_20;
        uint16_t wField_21;
        uint16_t wField_22;
        uint16_t wField_23;
        uint16_t wField_24;
        std::vector<uint8_t> bytesData_24;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallBuy(
        uint dwUniqueID,
        byte bytesData_1,
        byte byField_03,
        ushort wField_04,
        byte[] bytesData_4,
        byte byField_06,
        uint dwField_07,
        uint dwField_08,
        uint dwField_09,
        ushort wField_10,
        byte[] bytesData_10,
        byte byField_12,
        byte byField_13,
        byte[] bytesData_13,
        byte byField_15,
        byte byField_16,
        uint dwField_17,
        byte byField_18,
        uint dwField_19,
        ushort wField_20,
        ushort wField_21,
        ushort wField_22,
        ushort wField_23,
        ushort wField_24,
        byte[] bytesData_24
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallBuy {
        pub dw_unique_id: u32,
        pub bytes_data_1: u8,
        pub by_field_03: u8,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
        pub by_field_06: u8,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub w_field_10: u16,
        pub bytes_data_10: Vec<u8>,
        pub by_field_12: u8,
        pub by_field_13: u8,
        pub bytes_data_13: Vec<u8>,
        pub by_field_15: u8,
        pub by_field_16: u8,
        pub dw_field_17: u32,
        pub by_field_18: u8,
        pub dw_field_19: u32,
        pub w_field_20: u16,
        pub w_field_21: u16,
        pub w_field_22: u16,
        pub w_field_23: u16,
        pub w_field_24: u16,
        pub bytes_data_24: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallBuy struct {
        dwUniqueID uint32
        bytesData_1 uint8
        byField_03 uint8
        wField_04 uint16
        bytesData_4 []byte
        byField_06 uint8
        dwField_07 uint32
        dwField_08 uint32
        dwField_09 uint32
        wField_10 uint16
        bytesData_10 []byte
        byField_12 uint8
        byField_13 uint8
        bytesData_13 []byte
        byField_15 uint8
        byField_16 uint8
        dwField_17 uint32
        byField_18 uint8
        dwField_19 uint32
        wField_20 uint16
        wField_21 uint16
        wField_22 uint16
        wField_23 uint16
        wField_24 uint16
        bytesData_24 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallBuy {
        dwUniqueID: number;
        bytesData_1: number;
        byField_03: number;
        wField_04: number;
        bytesData_4: Uint8Array;
        byField_06: number;
        dwField_07: number;
        dwField_08: number;
        dwField_09: number;
        wField_10: number;
        bytesData_10: Uint8Array;
        byField_12: number;
        byField_13: number;
        bytesData_13: Uint8Array;
        byField_15: number;
        byField_16: number;
        dwField_17: number;
        byField_18: number;
        dwField_19: number;
        wField_20: number;
        wField_21: number;
        wField_22: number;
        wField_23: number;
        wField_24: number;
        bytesData_24: Uint8Array;
    }
    ```


# CLIENT_ENTITY_FULL_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F3` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881890` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088189E` |
| 2 | `dwField_02` | `u32` | 4 | `0x00996687` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `byField_05` | `u8` | 1 | `0x009966A4` |
| 6 | `dwField_06` | `u32` | 4 | `0x009966B2` |
| 7 | `dwField_07` | `u32` | 4 | `0x0099672B` |
| 8 | `byField_08` | `u8` | 1 | `0x00996739` |
| 9 | `byField_09` | `u8` | 1 | `0x00996747` |
| 10 | `dwField_10` | `u32` | 4 | `0x0099680A` |
| 11 | `wField_11` | `u16` | 2 | `0x00996818` |
| 12 | `bytesData_11` | `bytes` | variable | `0x0099686C` |
| 13 | `byField_13` | `u8` | 1 | `0x0099687A` |
| 14 | `byField_14` | `u8` | 1 | `0x00996888` |
| 15 | `dwField_15` | `u32` | 4 | `0x00996896` |
| 16 | `dwField_16` | `u32` | 4 | `0x009968A4` |
| 17 | `dwField_17` | `u32` | 4 | `0x009968B2` |
| 18 | `dwField_18` | `u32` | 4 | `0x009968C0` |
| 19 | `dwField_19` | `u32` | 4 | `0x009968CE` |
| 20 | `wField_20` | `u16` | 2 | `0x009968DC` |
| 21 | `bytesData_20` | `bytes` | variable | `0x0099691E` |
| 22 | `dwField_22` | `u32` | 4 | `0x0099692C` |
| 23 | `byField_23` | `u8` | 1 | `0x0099693A` |
| 24 | `byField_24` | `u8` | 1 | `0x00996948` |
| 25 | `byField_25` | `u8` | 1 | `0x00996A8F` |
| 26 | `dwField_26` | `u32` | 4 | `0x00996AA9` |
| 27 | `byField_27` | `u8` | 1 | `0x00996AB7` |
| 28 | `dwField_28` | `u32` | 4 | `0x00996AC5` |

**Minimum size**: 64 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] byField_05                     u8
  [   1] dwField_06                     u32
  [   5] dwField_07                     u32
  [   9] byField_08                     u8
  [  10] byField_09                     u8
  [  11] dwField_10                     u32
  [  15] wField_11                      u16
  [  17] bytesData_11                   bytes  (variable length)
  [   0] byField_13                     u8
  [   1] byField_14                     u8
  [   2] dwField_15                     u32
  [   6] dwField_16                     u32
  [  10] dwField_17                     u32
  [  14] dwField_18                     u32
  [  18] dwField_19                     u32
  [  22] wField_20                      u16
  [  24] bytesData_20                   bytes  (variable length)
  [   0] dwField_22                     u32
  [   4] byField_23                     u8
  [   5] byField_24                     u8
  [   6] byField_25                     u8
  [   7] dwField_26                     u32
  [  11] byField_27                     u8
  [  12] dwField_28                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityFullData {
        uint8_t byResult;
        uint32_t dwField_02;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
        uint8_t byField_05;
        uint32_t dwField_06;
        uint32_t dwField_07;
        uint8_t byField_08;
        uint8_t byField_09;
        uint32_t dwField_10;
        uint16_t wField_11;
        std::vector<uint8_t> bytesData_11;
        uint8_t byField_13;
        uint8_t byField_14;
        uint32_t dwField_15;
        uint32_t dwField_16;
        uint32_t dwField_17;
        uint32_t dwField_18;
        uint32_t dwField_19;
        uint16_t wField_20;
        std::vector<uint8_t> bytesData_20;
        uint32_t dwField_22;
        uint8_t byField_23;
        uint8_t byField_24;
        uint8_t byField_25;
        uint32_t dwField_26;
        uint8_t byField_27;
        uint32_t dwField_28;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityFullData(
        byte byResult,
        uint dwField_02,
        ushort wField_03,
        byte[] bytesData_3,
        byte byField_05,
        uint dwField_06,
        uint dwField_07,
        byte byField_08,
        byte byField_09,
        uint dwField_10,
        ushort wField_11,
        byte[] bytesData_11,
        byte byField_13,
        byte byField_14,
        uint dwField_15,
        uint dwField_16,
        uint dwField_17,
        uint dwField_18,
        uint dwField_19,
        ushort wField_20,
        byte[] bytesData_20,
        uint dwField_22,
        byte byField_23,
        byte byField_24,
        byte byField_25,
        uint dwField_26,
        byte byField_27,
        uint dwField_28
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityFullData {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
        pub by_field_05: u8,
        pub dw_field_06: u32,
        pub dw_field_07: u32,
        pub by_field_08: u8,
        pub by_field_09: u8,
        pub dw_field_10: u32,
        pub w_field_11: u16,
        pub bytes_data_11: Vec<u8>,
        pub by_field_13: u8,
        pub by_field_14: u8,
        pub dw_field_15: u32,
        pub dw_field_16: u32,
        pub dw_field_17: u32,
        pub dw_field_18: u32,
        pub dw_field_19: u32,
        pub w_field_20: u16,
        pub bytes_data_20: Vec<u8>,
        pub dw_field_22: u32,
        pub by_field_23: u8,
        pub by_field_24: u8,
        pub by_field_25: u8,
        pub dw_field_26: u32,
        pub by_field_27: u8,
        pub dw_field_28: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityFullData struct {
        byResult uint8
        dwField_02 uint32
        wField_03 uint16
        bytesData_3 []byte
        byField_05 uint8
        dwField_06 uint32
        dwField_07 uint32
        byField_08 uint8
        byField_09 uint8
        dwField_10 uint32
        wField_11 uint16
        bytesData_11 []byte
        byField_13 uint8
        byField_14 uint8
        dwField_15 uint32
        dwField_16 uint32
        dwField_17 uint32
        dwField_18 uint32
        dwField_19 uint32
        wField_20 uint16
        bytesData_20 []byte
        dwField_22 uint32
        byField_23 uint8
        byField_24 uint8
        byField_25 uint8
        dwField_26 uint32
        byField_27 uint8
        dwField_28 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityFullData {
        byResult: number;
        dwField_02: number;
        wField_03: number;
        bytesData_3: Uint8Array;
        byField_05: number;
        dwField_06: number;
        dwField_07: number;
        byField_08: number;
        byField_09: number;
        dwField_10: number;
        wField_11: number;
        bytesData_11: Uint8Array;
        byField_13: number;
        byField_14: number;
        dwField_15: number;
        dwField_16: number;
        dwField_17: number;
        dwField_18: number;
        dwField_19: number;
        wField_20: number;
        bytesData_20: Uint8Array;
        dwField_22: number;
        byField_23: number;
        byField_24: number;
        byField_25: number;
        dwField_26: number;
        byField_27: number;
        dwField_28: number;
    }
    ```


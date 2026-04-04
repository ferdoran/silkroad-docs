# SERVER_REGION_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3908` |
| Direction | Server → Client |
| Group | Game Extended 9 |
| Handler(s) | `0x00881D00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881D0E` |
| 2 | `bytesData_1` | `bytes` | variable | `0x0099D945` |
| 3 | `dwField_03` | `u32` | 4 | `0x0099D953` |
| 4 | `byField_04` | `u8` | 1 | `0x0099D961` |
| 5 | `dwField_05` | `u32` | 4 | `0x0099DA06` |
| 6 | `byField_06` | `u8` | 1 | `0x0099DA14` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
  [   0] dwField_03                     u32
  [   4] byField_04                     u8
  [   5] dwField_05                     u32
  [   9] byField_06                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RegionData {
        uint8_t byResult;
        std::vector<uint8_t> bytesData_1;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint8_t byField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RegionData(
        byte byResult,
        byte[] bytesData_1,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        byte byField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RegionData {
        pub by_result: u8,
        pub bytes_data_1: Vec<u8>,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub by_field_06: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type RegionData struct {
        byResult uint8
        bytesData_1 []byte
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        byField_06 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RegionData {
        byResult: number;
        bytesData_1: Uint8Array;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        byField_06: number;
    }
    ```


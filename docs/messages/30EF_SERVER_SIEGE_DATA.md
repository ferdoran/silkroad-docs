# SERVER_SIEGE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30EF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00885C20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885C5F` |
| 2 | `byField_02` | `u8` | 1 | `0x00885C7F` |
| 3 | `dwField_03` | `u32` | 4 | `0x00885D1F` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `dwField_06` | `u32` | 4 | `0x00885D3B` |
| 7 | `byField_07` | `u8` | 1 | `0x00885D49` |
| 8 | `wField_08` | `u16` | 2 | `0x00885E0A` |

**Minimum size**: 15 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] wField_04                      u16
  [   8] bytesData_4                    bytes  (variable length)
  [   0] dwField_06                     u32
  [   4] byField_07                     u8
  [   5] wField_08                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct SiegeData {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
        uint32_t dwField_06;
        uint8_t byField_07;
        uint16_t wField_08;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record SiegeData(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        ushort wField_04,
        byte[] bytesData_4,
        uint dwField_06,
        byte byField_07,
        ushort wField_08
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct SiegeData {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
        pub dw_field_06: u32,
        pub by_field_07: u8,
        pub w_field_08: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type SiegeData struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        wField_04 uint16
        bytesData_4 []byte
        dwField_06 uint32
        byField_07 uint8
        wField_08 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface SiegeData {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        wField_04: number;
        bytesData_4: Uint8Array;
        dwField_06: number;
        byField_07: number;
        wField_08: number;
    }
    ```


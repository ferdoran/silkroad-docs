# CLIENT_GUILD_REQUEST_2
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB308` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x00882030` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088203E` |
| 2 | `byField_02` | `u8` | 1 | `0x009976E1` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00997729` |
| 4 | `bytesData_3` | `bytes` | variable | `0x00997767` |
| 5 | `dwField_05` | `u32` | 4 | `0x00997775` |
| 6 | `dwField_06` | `u32` | 4 | `0x00997783` |
| 7 | `byField_07` | `u8` | 1 | `0x00997791` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] bytesData_2                    bytes  (variable length)
  [   0] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] dwField_06                     u32
  [   8] byField_07                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildRequest2 {
        uint8_t byResult;
        uint8_t byField_02;
        std::vector<uint8_t> bytesData_2;
        std::vector<uint8_t> bytesData_3;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint8_t byField_07;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildRequest2(
        byte byResult,
        byte byField_02,
        byte[] bytesData_2,
        byte[] bytesData_3,
        uint dwField_05,
        uint dwField_06,
        byte byField_07
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildRequest2 {
        pub by_result: u8,
        pub by_field_02: u8,
        pub bytes_data_2: Vec<u8>,
        pub bytes_data_3: Vec<u8>,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub by_field_07: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildRequest2 struct {
        byResult uint8
        byField_02 uint8
        bytesData_2 []byte
        bytesData_3 []byte
        dwField_05 uint32
        dwField_06 uint32
        byField_07 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildRequest2 {
        byResult: number;
        byField_02: number;
        bytesData_2: Uint8Array;
        bytesData_3: Uint8Array;
        dwField_05: number;
        dwField_06: number;
        byField_07: number;
    }
    ```


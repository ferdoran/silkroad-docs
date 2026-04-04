# SERVER_COS_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x315A` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008992B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x008992D4` |
| 2 | `dwField_02` | `u32` | 4 | `0x008992E2` |
| 3 | `dwField_03` | `u32` | 4 | `0x008992F0` |
| 4 | `byField_04` | `u8` | 1 | `0x008992FE` |

**Minimum size**: 9 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] dwField_03                     u32
  [   8] byField_04                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosUpdate {
        std::vector<uint8_t> bytesData;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosUpdate(
        byte[] bytesData,
        uint dwField_02,
        uint dwField_03,
        byte byField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosUpdate {
        pub bytes_data: Vec<u8>,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosUpdate struct {
        bytesData []byte
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosUpdate {
        bytesData: Uint8Array;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
    }
    ```


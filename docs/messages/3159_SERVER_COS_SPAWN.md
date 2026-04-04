# SERVER_COS_SPAWN
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3159` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008990C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x008990E5` |
| 2 | `byField_02` | `u8` | 1 | `0x008990F3` |
| 3 | `byField_03` | `u8` | 1 | `0x00899101` |
| 4 | `wField_04` | `u16` | 2 | `0x0089911C` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089915B` |
| 6 | `dwField_06` | `u32` | 4 | `0x00899169` |

**Minimum size**: 12 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] byField_02                     u8
  [   1] byField_03                     u8
  [   2] wField_04                      u16
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosSpawn {
        std::vector<uint8_t> bytesData;
        uint8_t byField_02;
        uint8_t byField_03;
        uint16_t wField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosSpawn(
        byte[] bytesData,
        byte byField_02,
        byte byField_03,
        ushort wField_04,
        uint dwField_05,
        uint dwField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosSpawn {
        pub bytes_data: Vec<u8>,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub w_field_04: u16,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosSpawn struct {
        bytesData []byte
        byField_02 uint8
        byField_03 uint8
        wField_04 uint16
        dwField_05 uint32
        dwField_06 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosSpawn {
        bytesData: Uint8Array;
        byField_02: number;
        byField_03: number;
        wField_04: number;
        dwField_05: number;
        dwField_06: number;
    }
    ```


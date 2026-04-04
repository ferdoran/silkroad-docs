# CLIENT_ENTITY_REGION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0FC` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087FD00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0099A85F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0099A86F` |
| 3 | `dwField_03` | `u32` | 4 | `0x0099A87D` |
| 4 | `byField_04` | `u8` | 1 | `0x0099A88B` |
| 5 | `dwField_05` | `u32` | 4 | `0x0099A8EB` |
| 6 | `wField_06` | `u16` | 2 | `0x0099A8F9` |
| 7 | `bytesData_6` | `bytes` | variable | `0x0099A93A` |
| 8 | `byField_08` | `u8` | 1 | `0x0099A948` |
| 9 | `wField_09` | `u16` | 2 | `0x0099A956` |
| 10 | `bytesData_9` | `bytes` | variable | `0x0099A994` |
| 11 | `dwField_11` | `u32` | 4 | `0x0099A9A2` |
| 12 | `byField_12` | `u8` | 1 | `0x0099A9B0` |

**Minimum size**: 27 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
  [  13] dwField_05                     u32
  [  17] wField_06                      u16
  [  19] bytesData_6                    bytes  (variable length)
  [   0] byField_08                     u8
  [   1] wField_09                      u16
  [   3] bytesData_9                    bytes  (variable length)
  [   0] dwField_11                     u32
  [   4] byField_12                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityRegion {
        uint32_t dwUniqueID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint16_t wField_06;
        std::vector<uint8_t> bytesData_6;
        uint8_t byField_08;
        uint16_t wField_09;
        std::vector<uint8_t> bytesData_9;
        uint32_t dwField_11;
        uint8_t byField_12;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityRegion(
        uint dwUniqueID,
        uint dwField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        ushort wField_06,
        byte[] bytesData_6,
        byte byField_08,
        ushort wField_09,
        byte[] bytesData_9,
        uint dwField_11,
        byte byField_12
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityRegion {
        pub dw_unique_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub w_field_06: u16,
        pub bytes_data_6: Vec<u8>,
        pub by_field_08: u8,
        pub w_field_09: u16,
        pub bytes_data_9: Vec<u8>,
        pub dw_field_11: u32,
        pub by_field_12: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityRegion struct {
        dwUniqueID uint32
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        wField_06 uint16
        bytesData_6 []byte
        byField_08 uint8
        wField_09 uint16
        bytesData_9 []byte
        dwField_11 uint32
        byField_12 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityRegion {
        dwUniqueID: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        wField_06: number;
        bytesData_6: Uint8Array;
        byField_08: number;
        wField_09: number;
        bytesData_9: Uint8Array;
        dwField_11: number;
        byField_12: number;
    }
    ```


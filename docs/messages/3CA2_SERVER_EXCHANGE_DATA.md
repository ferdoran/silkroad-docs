# SERVER_EXCHANGE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3CA2` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x00884CA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00884D14` |
| 2 | `byField_02` | `u8` | 1 | `0x00884D22` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `byField_05` | `u8` | 1 | `0x0060135B` |
| 6 | `dwField_06` | `u32` | 4 | `0x00601371` |
| 7 | `dwField_07` | `u32` | 4 | `0x0060138C` |
| 8 | `dwField_08` | `u32` | 4 | `0x006013A6` |
| 9 | `dwField_09` | `u32` | 4 | `0x006013C1` |

**Minimum size**: 24 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byField_02                     u8
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] byField_05                     u8
  [   1] dwField_06                     u32
  [   5] dwField_07                     u32
  [   9] dwField_08                     u32
  [  13] dwField_09                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeData {
        uint32_t dwRefObjID;
        uint8_t byField_02;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
        uint8_t byField_05;
        uint32_t dwField_06;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeData(
        uint dwRefObjID,
        byte byField_02,
        ushort wField_03,
        byte[] bytesData_3,
        byte byField_05,
        uint dwField_06,
        uint dwField_07,
        uint dwField_08,
        uint dwField_09
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeData {
        pub dw_ref_obj_id: u32,
        pub by_field_02: u8,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
        pub by_field_05: u8,
        pub dw_field_06: u32,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ExchangeData struct {
        dwRefObjID uint32
        byField_02 uint8
        wField_03 uint16
        bytesData_3 []byte
        byField_05 uint8
        dwField_06 uint32
        dwField_07 uint32
        dwField_08 uint32
        dwField_09 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeData {
        dwRefObjID: number;
        byField_02: number;
        wField_03: number;
        bytesData_3: Uint8Array;
        byField_05: number;
        dwField_06: number;
        dwField_07: number;
        dwField_08: number;
        dwField_09: number;
    }
    ```


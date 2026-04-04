# SERVER_STALL_CLOSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3C86` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089BCC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x0089BD06` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089BD30` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089BD3E` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089BDAC` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089BDBA` |

**Minimum size**: 16 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_CTL_TC_SAVE_BUFF_TIME_OVER` | UI |

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] dwField_03                     u32
  [   8] dwField_04                     u32
  [  12] dwField_05                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallClose {
        std::vector<uint8_t> bytesData;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint32_t dwField_04;
        uint32_t dwField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallClose(
        byte[] bytesData,
        uint dwField_02,
        uint dwField_03,
        uint dwField_04,
        uint dwField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallClose {
        pub bytes_data: Vec<u8>,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub dw_field_04: u32,
        pub dw_field_05: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallClose struct {
        bytesData []byte
        dwField_02 uint32
        dwField_03 uint32
        dwField_04 uint32
        dwField_05 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallClose {
        bytesData: Uint8Array;
        dwField_02: number;
        dwField_03: number;
        dwField_04: number;
        dwField_05: number;
    }
    ```


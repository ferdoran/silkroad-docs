# SERVER_ACADEMY_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3256` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088F9E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088FA5D` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088FA77` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088FA85` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `wField_06` | `u16` | 2 | `0x0088FC65` |

**Minimum size**: 13 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_GUILD_NAME_GRANT_RESULT` | UI |
| `UIIT_STT_CONFIRM_BOX` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] wField_04                      u16
  [  11] bytesData_4                    bytes  (variable length)
  [   0] wField_06                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyUpdate {
        uint8_t byResult;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
        uint16_t wField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyUpdate(
        byte byResult,
        uint dwField_02,
        uint dwField_03,
        ushort wField_04,
        byte[] bytesData_4,
        ushort wField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyUpdate {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
        pub w_field_06: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyUpdate struct {
        byResult uint8
        dwField_02 uint32
        dwField_03 uint32
        wField_04 uint16
        bytesData_4 []byte
        wField_06 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyUpdate {
        byResult: number;
        dwField_02: number;
        dwField_03: number;
        wField_04: number;
        bytesData_4: Uint8Array;
        wField_06: number;
    }
    ```


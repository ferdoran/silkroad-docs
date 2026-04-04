# SERVER_ACADEMY_LIST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3257` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008905D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00890668` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyList {
        uint32_t dwRefObjID;
        uint16_t wField_02;
        std::vector<uint8_t> bytesData_2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyList(
        uint dwRefObjID,
        ushort wField_02,
        byte[] bytesData_2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyList {
        pub dw_ref_obj_id: u32,
        pub w_field_02: u16,
        pub bytes_data_2: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyList struct {
        dwRefObjID uint32
        wField_02 uint16
        bytesData_2 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyList {
        dwRefObjID: number;
        wField_02: number;
        bytesData_2: Uint8Array;
    }
    ```


# CLIENT_ACADEMY_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB251` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x0088F630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088F679` |
| 2 | `wSlotID` | `bytes` | variable | `0x00841948` |
| 3 | `wField_03` | `u16` | 2 | `0x0088F70D` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 5 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_GUILD_WAREHOUSE_USE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wSlotID                        bytes  (variable length)
  [   0] wField_03                      u16
  [   2] wField_04                      u16
  [   4] bytesData_4                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyDetail {
        uint8_t byResult;
        std::vector<uint8_t> wSlotID;
        uint16_t wField_03;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyDetail(
        byte byResult,
        byte[] wSlotID,
        ushort wField_03,
        ushort wField_04,
        byte[] bytesData_4
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyDetail {
        pub by_result: u8,
        pub w_slot_id: Vec<u8>,
        pub w_field_03: u16,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyDetail struct {
        byResult uint8
        wSlotID []byte
        wField_03 uint16
        wField_04 uint16
        bytesData_4 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyDetail {
        byResult: number;
        wSlotID: Uint8Array;
        wField_03: number;
        wField_04: number;
        bytesData_4: Uint8Array;
    }
    ```


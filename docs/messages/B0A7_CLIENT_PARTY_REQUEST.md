# CLIENT_PARTY_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0A7` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873D60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x00873DCA` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyRequest {
        uint32_t dwUniqueID;
        uint16_t wField_02;
        std::vector<uint8_t> bytesData_2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyRequest(
        uint dwUniqueID,
        ushort wField_02,
        byte[] bytesData_2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyRequest {
        pub dw_unique_id: u32,
        pub w_field_02: u16,
        pub bytes_data_2: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyRequest struct {
        dwUniqueID uint32
        wField_02 uint16
        bytesData_2 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyRequest {
        dwUniqueID: number;
        wField_02: number;
        bytesData_2: Uint8Array;
    }
    ```


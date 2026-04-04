# CLIENT_PARTY_MEMBER
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB304` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x00885E50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885E8D` |
| 2 | `wMemberID` | `u16` | 2 | `0x00885EB1` |
| 3 | `byAction` | `u8` | 1 | `0x00885ECD` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_FRIENDERR_REFUSAL` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wMemberID                      u16
  [   3] byAction                       u8
  [   4] wField_04                      u16
  [   6] bytesData_4                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyMember {
        uint8_t byResult;
        uint16_t wMemberID;
        uint8_t byAction;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyMember(
        byte byResult,
        ushort wMemberID,
        byte byAction,
        ushort wField_04,
        byte[] bytesData_4
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyMember {
        pub by_result: u8,
        pub w_member_id: u16,
        pub by_action: u8,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyMember struct {
        byResult uint8
        wMemberID uint16
        byAction uint8
        wField_04 uint16
        bytesData_4 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyMember {
        byResult: number;
        wMemberID: number;
        byAction: number;
        wField_04: number;
        bytesData_4: Uint8Array;
    }
    ```


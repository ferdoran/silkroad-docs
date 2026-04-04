# CLIENT_TITLE_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E4` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00889370` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008893B2` |
| 2 | `byAction` | `u8` | 1 | `0x008893FE` |
| 3 | `wTitleID` | `u16` | 2 | `0x004F7A7D` |
| 4 | `byExtra` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x0088960A` |
| 6 | `byField_06` | `u8` | 1 | `0x00889618` |

**Minimum size**: 7 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_ALIAS_MODIFY_COMPLETE` | UI |
| `UIIT_MSG_ALIAS_CREATE_COMPLETE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] wTitleID                       u16
  [   4] byExtra                        bytes  (variable length)
  [   0] wField_05                      u16
  [   2] byField_06                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TitleRequest {
        uint8_t byResult;
        uint8_t byAction;
        uint16_t wTitleID;
        std::vector<uint8_t> byExtra;
        uint16_t wField_05;
        uint8_t byField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TitleRequest(
        byte byResult,
        byte byAction,
        ushort wTitleID,
        byte[] byExtra,
        ushort wField_05,
        byte byField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TitleRequest {
        pub by_result: u8,
        pub by_action: u8,
        pub w_title_id: u16,
        pub by_extra: Vec<u8>,
        pub w_field_05: u16,
        pub by_field_06: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type TitleRequest struct {
        byResult uint8
        byAction uint8
        wTitleID uint16
        byExtra []byte
        wField_05 uint16
        byField_06 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TitleRequest {
        byResult: number;
        byAction: number;
        wTitleID: number;
        byExtra: Uint8Array;
        wField_05: number;
        byField_06: number;
    }
    ```


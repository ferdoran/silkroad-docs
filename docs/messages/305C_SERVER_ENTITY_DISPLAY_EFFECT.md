# SERVER_ENTITY_DISPLAY_EFFECT

> Previously documented as `SERVER_ENTITY_NAME` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x305C` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00873990` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesOldName` | `bytes` | variable | `0x008739F6` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x00873A04` |
| 3 | `bytesNewName` | `bytes` | variable | `0x00873A82` |
| 4 | `wRegionID` | `u16` | 2 | `0x00873AE8` |
| 5 | `byFlag` | `u8` | 1 | `0x00873AFC` |

**Minimum size**: 7 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_STATE_GET_ITEM_EXPENDABLE` | UI |
| `UIIT_MSG_PARTYGET_ITEM_EXPENDABLE` | UI |
| `UIIT_MSG_PARTYGET_GOLD` | UI |

### Structure Summary

```
  [   0] bytesOldName                   bytes  (variable length)
  [   0] dwUniqueID                     u32
  [   4] bytesNewName                   bytes  (variable length)
  [   0] wRegionID                      u16
  [   2] byFlag                         u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityName {
        std::vector<uint8_t> bytesOldName;
        uint32_t dwUniqueID;
        std::vector<uint8_t> bytesNewName;
        uint16_t wRegionID;
        uint8_t byFlag;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityName(
        byte[] bytesOldName,
        uint dwUniqueID,
        byte[] bytesNewName,
        ushort wRegionID,
        byte byFlag
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityName {
        pub bytes_old_name: Vec<u8>,
        pub dw_unique_id: u32,
        pub bytes_new_name: Vec<u8>,
        pub w_region_id: u16,
        pub by_flag: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityName struct {
        bytesOldName []byte
        dwUniqueID uint32
        bytesNewName []byte
        wRegionID uint16
        byFlag uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityName {
        bytesOldName: Uint8Array;
        dwUniqueID: number;
        bytesNewName: Uint8Array;
        wRegionID: number;
        byFlag: number;
    }
    ```


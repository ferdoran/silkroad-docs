# CLIENT_ARENA_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB256` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x00895530` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089557B` |
| 2 | `byAction` | `u8` | 1 | `0x00895595` |
| 3 | `wItemID` | `u16` | 2 | `0x004F7A7D` |
| 4 | `wExtraParam` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x00895625` |
| 6 | `wField_06` | `u16` | 2 | `0x008957A2` |

**Minimum size**: 8 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_LETTER_SENDOK` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] wItemID                        u16
  [   4] wExtraParam                    bytes  (variable length)
  [   0] wField_05                      u16
  [   2] wField_06                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaUpdate {
        uint8_t byResult;
        uint8_t byAction;
        uint16_t wItemID;
        std::vector<uint8_t> wExtraParam;
        uint16_t wField_05;
        uint16_t wField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaUpdate(
        byte byResult,
        byte byAction,
        ushort wItemID,
        byte[] wExtraParam,
        ushort wField_05,
        ushort wField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaUpdate {
        pub by_result: u8,
        pub by_action: u8,
        pub w_item_id: u16,
        pub w_extra_param: Vec<u8>,
        pub w_field_05: u16,
        pub w_field_06: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaUpdate struct {
        byResult uint8
        byAction uint8
        wItemID uint16
        wExtraParam []byte
        wField_05 uint16
        wField_06 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaUpdate {
        byResult: number;
        byAction: number;
        wItemID: number;
        wExtraParam: Uint8Array;
        wField_05: number;
        wField_06: number;
    }
    ```


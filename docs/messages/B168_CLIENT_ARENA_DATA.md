# CLIENT_ARENA_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB168` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0089C3A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bySlotType` | `u8` | 1 | `0x0089C41E` |
| 2 | `byItemType` | `u8` | 1 | `0x0089C42C` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 4 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_CHAT_WHISPER_BLOCK` | UI |
| `UIIT_MSG_CHAT_WHISPER_ADMISSION` | UI |
| `UIIT_MSG_COSPETERR_PETNAME_SUMENESS` | UI |
| `UIIT_MSG_ALIAS_ACTION_ERR_NOTALLOW` | UI |
| `UIIT_STT_BLOCKMAN_DELETE_LISTFULL` | UI |

### Structure Summary

```
  [   0] bySlotType                     u8
  [   1] byItemType                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaData {
        uint8_t bySlotType;
        uint8_t byItemType;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaData(
        byte bySlotType,
        byte byItemType,
        ushort wField_03,
        byte[] bytesData_3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaData {
        pub by_slot_type: u8,
        pub by_item_type: u8,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaData struct {
        bySlotType uint8
        byItemType uint8
        wField_03 uint16
        bytesData_3 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaData {
        bySlotType: number;
        byItemType: number;
        wField_03: number;
        bytesData_3: Uint8Array;
    }
    ```


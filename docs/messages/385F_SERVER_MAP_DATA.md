# SERVER_MAP_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x385F` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x00890210` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089027E` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |
| 4 | `byField_04` | `u8` | 1 | `0x0089029B` |

**Minimum size**: 7 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_FORT_GUILD_COMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_SUBCOMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_BATTLEMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_PRODUCTMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_TRAINERMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_ENGINEER` | UI |

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
  [   0] byField_04                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MapData {
        uint32_t dwRefObjID;
        uint16_t wField_02;
        std::vector<uint8_t> bytesData_2;
        uint8_t byField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MapData(
        uint dwRefObjID,
        ushort wField_02,
        byte[] bytesData_2,
        byte byField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MapData {
        pub dw_ref_obj_id: u32,
        pub w_field_02: u16,
        pub bytes_data_2: Vec<u8>,
        pub by_field_04: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type MapData struct {
        dwRefObjID uint32
        wField_02 uint16
        bytesData_2 []byte
        byField_04 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MapData {
        dwRefObjID: number;
        wField_02: number;
        bytesData_2: Uint8Array;
        byField_04: number;
    }
    ```


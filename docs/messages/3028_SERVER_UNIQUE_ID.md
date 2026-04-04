# SERVER_UNIQUE_ID
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3028` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4F80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A4F92` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A4FA0` |
| 3 | `bytesData` | `bytes[14]` | 14 | `0x008A4FAE` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wRegionID                      u16
  [   6] bytesData                      bytes[14]
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct UniqueId {
        uint32_t dwUniqueID;
        uint16_t wRegionID;
        uint8_t bytesData;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record UniqueId(
        uint dwUniqueID,
        ushort wRegionID,
        byte bytesData
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct UniqueId {
        pub dw_unique_id: u32,
        pub w_region_id: u16,
        pub bytes_data: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type UniqueId struct {
        dwUniqueID uint32
        wRegionID uint16
        bytesData uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface UniqueId {
        dwUniqueID: number;
        wRegionID: number;
        bytesData: number;
    }
    ```


# CLIENT_UNIQUE_ID
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB04F` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A50E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wRegionID` | `u16` | 2 | `0x008A50F1` |
| 2 | `bytesPosition` | `bytes[14]` | 14 | `0x008A50FF` |
| 3 | `dwUniqueID` | `u32` | 4 | `0x008A510D` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] wRegionID                      u16
  [   2] bytesPosition                  bytes[14]
  [  16] dwUniqueID                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct UniqueId {
        uint16_t wRegionID;
        uint8_t bytesPosition;
        uint32_t dwUniqueID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record UniqueId(
        ushort wRegionID,
        byte bytesPosition,
        uint dwUniqueID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct UniqueId {
        pub w_region_id: u16,
        pub bytes_position: u8,
        pub dw_unique_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type UniqueId struct {
        wRegionID uint16
        bytesPosition uint8
        dwUniqueID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface UniqueId {
        wRegionID: number;
        bytesPosition: number;
        dwUniqueID: number;
    }
    ```


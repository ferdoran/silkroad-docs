# SERVER_STORAGE_DATA_BEGIN

> **Corrected name** (server RE): Was `SERVER_ENTITY_UPDATE_POSITION` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3047` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008AC3D0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `StorageGold` | `u64` | 8 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A6D32` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A6D48` |
| 3 | `dwPosX` | `u32` | 4 | `0x008A6BE2` |
| 4 | `wAngle` | `u16` | 2 | `0x008A6C00` |
| 5 | `dwPosZ` | `u32` | 4 | `0x008A6C41` |
| 6 | `wDestRegion` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 15 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] wRegionID                      u16
  [   3] dwPosX                         u32
  [   7] wAngle                         u16
  [   9] dwPosZ                         u32
  [  13] wDestRegion                    u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StorageDataBegin {
        uint8_t byResult;
        uint16_t wRegionID;
        uint32_t dwPosX;
        uint16_t wAngle;
        uint32_t dwPosZ;
        uint16_t wDestRegion;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StorageDataBegin(
        byte byResult,
        ushort wRegionID,
        uint dwPosX,
        ushort wAngle,
        uint dwPosZ,
        ushort wDestRegion
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StorageDataBegin {
        pub by_result: u8,
        pub w_region_id: u16,
        pub dw_pos_x: u32,
        pub w_angle: u16,
        pub dw_pos_z: u32,
        pub w_dest_region: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type StorageDataBegin struct {
        byResult uint8
        wRegionID uint16
        dwPosX uint32
        wAngle uint16
        dwPosZ uint32
        wDestRegion uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StorageDataBegin {
        byResult: number;
        wRegionID: number;
        dwPosX: number;
        wAngle: number;
        dwPosZ: number;
        wDestRegion: number;
    }
    ```


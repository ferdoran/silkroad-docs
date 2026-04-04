# SERVER_ENTITY_DESPAWN

> **Corrected name** (server RE): Was `SERVER_CHARACTER_RESTORE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3016` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6CA0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `uniqueID` | `u32` | 4 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A6BE2` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A6C00` |
| 3 | `dwRealTime` | `u32` | 4 | `0x008A6C41` |
| 4 | `wDay` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 12 bytes

</details>
### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wRegionID                      u16
  [   6] dwRealTime                     u32
  [  10] wDay                           u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityDespawn {
        uint32_t dwRefObjID;
        uint16_t wRegionID;
        uint32_t dwRealTime;
        uint16_t wDay;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityDespawn(
        uint dwRefObjID,
        ushort wRegionID,
        uint dwRealTime,
        ushort wDay
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityDespawn {
        pub dw_ref_obj_id: u32,
        pub w_region_id: u16,
        pub dw_real_time: u32,
        pub w_day: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityDespawn struct {
        dwRefObjID uint32
        wRegionID uint16
        dwRealTime uint32
        wDay uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityDespawn {
        dwRefObjID: number;
        wRegionID: number;
        dwRealTime: number;
        wDay: number;
    }
    ```


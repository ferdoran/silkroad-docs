# SERVER_ENTITY_UPDATE_EXP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3076` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6CC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A6CCC` |
| 2 | `byUpdateType` | `u8` | 1 | `0x008A6D32` |
| 3 | `wRegionID` | `u16` | 2 | `0x008A6D48` |
| 4 | `dwRealTime` | `u32` | 4 | `0x008A6BE2` |
| 5 | `wDay` | `u16` | 2 | `0x008A6C00` |
| 6 | `dwParam1` | `u32` | 4 | `0x008A6C41` |
| 7 | `wParam2` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 19 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byUpdateType                   u8
  [   5] wRegionID                      u16
  [   7] dwRealTime                     u32
  [  11] wDay                           u16
  [  13] dwParam1                       u32
  [  17] wParam2                        u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateExp {
        uint32_t dwRefObjID;
        uint8_t byUpdateType;
        uint16_t wRegionID;
        uint32_t dwRealTime;
        uint16_t wDay;
        uint32_t dwParam1;
        uint16_t wParam2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateExp(
        uint dwRefObjID,
        byte byUpdateType,
        ushort wRegionID,
        uint dwRealTime,
        ushort wDay,
        uint dwParam1,
        ushort wParam2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateExp {
        pub dw_ref_obj_id: u32,
        pub by_update_type: u8,
        pub w_region_id: u16,
        pub dw_real_time: u32,
        pub w_day: u16,
        pub dw_param1: u32,
        pub w_param2: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateExp struct {
        dwRefObjID uint32
        byUpdateType uint8
        wRegionID uint16
        dwRealTime uint32
        wDay uint16
        dwParam1 uint32
        wParam2 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateExp {
        dwRefObjID: number;
        byUpdateType: number;
        wRegionID: number;
        dwRealTime: number;
        wDay: number;
        dwParam1: number;
        wParam2: number;
    }
    ```


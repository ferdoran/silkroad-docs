# SERVER_ENTITY_STATE_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3206` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008A4990` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00A56731` |
| 2 | `dwField_02` | `u32` | 4 | `0x00A5673F` |
| 3 | `wField_03` | `u16` | 2 | `0x00A5674D` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] wField_03                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityStateUpdate {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint16_t wField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStateUpdate(
        uint dwRefObjID,
        uint dwField_02,
        ushort wField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStateUpdate {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub w_field_03: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStateUpdate struct {
        dwRefObjID uint32
        dwField_02 uint32
        wField_03 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStateUpdate {
        dwRefObjID: number;
        dwField_02: number;
        wField_03: number;
    }
    ```


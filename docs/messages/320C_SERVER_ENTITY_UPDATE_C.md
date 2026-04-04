# SERVER_ENTITY_UPDATE_C
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x320C` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088F880` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0088F8C8` |
| 2 | `wField_02` | `u16` | 2 | `0x0088F8D6` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateC {
        uint32_t dwRefObjID;
        uint16_t wField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateC(
        uint dwRefObjID,
        ushort wField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateC {
        pub dw_ref_obj_id: u32,
        pub w_field_02: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateC struct {
        dwRefObjID uint32
        wField_02 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateC {
        dwRefObjID: number;
        wField_02: number;
    }
    ```


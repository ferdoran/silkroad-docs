# SERVER_ENTITY_UPDATE_B
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x320B` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00898FF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899019` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899027` |
| 3 | `dwField_03` | `u32` | 4 | `0x00899035` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateB {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateB(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateB {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateB struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateB {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
    }
    ```


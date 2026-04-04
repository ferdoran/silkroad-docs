# SERVER_COS_SETTINGS
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x315D` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00899480` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089949B` |
| 2 | `dwField_02` | `u32` | 4 | `0x008994A9` |
| 3 | `dwField_03` | `u32` | 4 | `0x008994B7` |

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
    struct CosSettings {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosSettings(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosSettings {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosSettings struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosSettings {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
    }
    ```


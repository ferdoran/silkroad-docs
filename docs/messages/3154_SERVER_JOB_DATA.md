# SERVER_JOB_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3154` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00882DE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00882DFF` |
| 2 | `dwField_02` | `u32` | 4 | `0x00882E0D` |
| 3 | `dwField_03` | `u32` | 4 | `0x00882E1B` |

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
    struct JobData {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobData(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobData {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobData struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobData {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
    }
    ```


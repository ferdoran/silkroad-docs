# SERVER_COS_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x315B` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00899350` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899373` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899381` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089938F` |
| 4 | `byField_04` | `u8` | 1 | `0x0089939D` |

**Total size**: 13 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosData {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosData(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03,
        byte byField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosData {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosData struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosData {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
    }
    ```


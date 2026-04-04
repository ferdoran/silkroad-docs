# SERVER_ARENA_RESULT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x325E` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00899E60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899E87` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899E95` |
| 3 | `dwField_03` | `u32` | 4 | `0x00899EA3` |
| 4 | `byField_04` | `u8` | 1 | `0x00899EB1` |

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
    struct ArenaResult {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaResult(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03,
        byte byField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaResult {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaResult struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaResult {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
    }
    ```


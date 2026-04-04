# SERVER_ARENA_SCORE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3261` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0089A0D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089A0F1` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089A103` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089A111` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089A11F` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089A12D` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] dwField_05                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaScore {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint32_t dwField_04;
        uint32_t dwField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaScore(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03,
        uint dwField_04,
        uint dwField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaScore {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub dw_field_04: u32,
        pub dw_field_05: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaScore struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
        dwField_04 uint32
        dwField_05 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaScore {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
        dwField_04: number;
        dwField_05: number;
    }
    ```


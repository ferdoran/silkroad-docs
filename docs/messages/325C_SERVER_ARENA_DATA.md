# SERVER_ARENA_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x325C` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00899580` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089958E` |
| 2 | `dwField_02` | `u32` | 4 | `0x008995A4` |
| 3 | `dwField_03` | `u32` | 4 | `0x008995B2` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaData {
        uint8_t byResult;
        uint32_t dwField_02;
        uint32_t dwField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaData(
        byte byResult,
        uint dwField_02,
        uint dwField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaData {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaData struct {
        byResult uint8
        dwField_02 uint32
        dwField_03 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaData {
        byResult: number;
        dwField_02: number;
        dwField_03: number;
    }
    ```


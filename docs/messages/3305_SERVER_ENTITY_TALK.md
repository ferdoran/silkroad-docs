# SERVER_ENTITY_TALK
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3305` |
| Direction | Server → Client |
| Group | Game Extended 3 |
| Handler(s) | `0x0088A770` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088A781` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088A78F` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityTalk {
        uint8_t byResult;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityTalk(
        byte byResult,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityTalk {
        pub by_result: u8,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityTalk struct {
        byResult uint8
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityTalk {
        byResult: number;
        dwField_02: number;
    }
    ```


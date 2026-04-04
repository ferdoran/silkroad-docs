# CLIENT_ENTITY_RESURRECT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F8` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881820` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088182E` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityResurrect {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityResurrect(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityResurrect {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityResurrect struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityResurrect {
        byResult: number;
    }
    ```


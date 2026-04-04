# SERVER_FORTRESS_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x34F2` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0089A540` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A54B` |

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
    struct FortressAction {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressAction(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressAction {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressAction struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressAction {
        byResult: number;
    }
    ```


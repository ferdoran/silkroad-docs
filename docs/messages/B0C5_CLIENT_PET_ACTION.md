# CLIENT_PET_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0C5` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880B10` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880B1E` |

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
    struct PetAction {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetAction(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetAction {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetAction struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetAction {
        byResult: number;
    }
    ```


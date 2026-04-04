# CLIENT_ENTITY_STATUS
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F4` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008819E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008819EE` |

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
    struct EntityStatus {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStatus(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStatus {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStatus struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStatus {
        byResult: number;
    }
    ```


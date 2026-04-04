# SERVER_ENTITY_LEVEL_UP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3077` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088E1C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088E1CE` |
| 2 | `wNewLevel` | `u16` | 2 | `0x0088E1E3` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wNewLevel                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityLevelUp {
        uint8_t byResult;
        uint16_t wNewLevel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityLevelUp(
        byte byResult,
        ushort wNewLevel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityLevelUp {
        pub by_result: u8,
        pub w_new_level: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityLevelUp struct {
        byResult uint8
        wNewLevel uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityLevelUp {
        byResult: number;
        wNewLevel: number;
    }
    ```


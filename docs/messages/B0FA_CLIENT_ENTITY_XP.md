# CLIENT_ENTITY_XP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0FA` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881AE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881B05` |
| 2 | `dwMinLevel` | `u32` | 4 | `0x00881B1B` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_GUILD_GP_SUBSCRIPION_RESULT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwMinLevel                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityXp {
        uint8_t byResult;
        uint32_t dwMinLevel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityXp(
        byte byResult,
        uint dwMinLevel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityXp {
        pub by_result: u8,
        pub dw_min_level: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityXp struct {
        byResult uint8
        dwMinLevel uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityXp {
        byResult: number;
        dwMinLevel: number;
    }
    ```


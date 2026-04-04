# CLIENT_ARENA_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB259` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x0088D750` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D775` |
| 2 | `dwMinLevel` | `u32` | 4 | `0x0088D78B` |

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
    struct ArenaInfo {
        uint8_t byResult;
        uint32_t dwMinLevel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaInfo(
        byte byResult,
        uint dwMinLevel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaInfo {
        pub by_result: u8,
        pub dw_min_level: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaInfo struct {
        byResult uint8
        dwMinLevel uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaInfo {
        byResult: number;
        dwMinLevel: number;
    }
    ```


# SERVER_GUILD_PLAYER_LOG

> Previously documented as `SERVER_ENTITY_UPDATE_SP` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x30FF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00881950` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088195E` |
| 2 | `wSP` | `u16` | 2 | `0x00881985` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wSP                            u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateSp {
        uint8_t byResult;
        uint16_t wSP;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateSp(
        byte byResult,
        ushort wSP
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateSp {
        pub by_result: u8,
        pub w_sp: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateSp struct {
        byResult uint8
        wSP uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateSp {
        byResult: number;
        wSP: number;
    }
    ```


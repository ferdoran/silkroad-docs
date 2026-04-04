# SERVER_ENTITY_BERSERK
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30EB` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880B60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00880B70` |
| 2 | `byLevel` | `u8` | 1 | `0x00880B7E` |
| 3 | `wDuration` | `u16` | 2 | `0x00880BB5` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] byLevel                        u8
  [   2] wDuration                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityBerserk {
        uint8_t byAction;
        uint8_t byLevel;
        uint16_t wDuration;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityBerserk(
        byte byAction,
        byte byLevel,
        ushort wDuration
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityBerserk {
        pub by_action: u8,
        pub by_level: u8,
        pub w_duration: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityBerserk struct {
        byAction uint8
        byLevel uint8
        wDuration uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityBerserk {
        byAction: number;
        byLevel: number;
        wDuration: number;
    }
    ```


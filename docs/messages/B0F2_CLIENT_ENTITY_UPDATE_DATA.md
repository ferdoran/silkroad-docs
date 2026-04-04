# CLIENT_ENTITY_UPDATE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F2` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008819B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwGuildID` | `u32` | 4 | `0x008819BB` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwGuildID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateData {
        uint32_t dwGuildID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateData(
        uint dwGuildID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateData {
        pub dw_guild_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateData struct {
        dwGuildID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateData {
        dwGuildID: number;
    }
    ```


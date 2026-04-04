# SERVER_ENTITY_UPDATE_PVP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3122` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0089BAE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwKills` | `u32` | 4 | `0x0089BB3A` |
| 2 | `dwDeaths` | `u32` | 4 | `0x0089BB48` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwKills                        u32
  [   4] dwDeaths                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdatePvp {
        uint32_t dwKills;
        uint32_t dwDeaths;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdatePvp(
        uint dwKills,
        uint dwDeaths
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdatePvp {
        pub dw_kills: u32,
        pub dw_deaths: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdatePvp struct {
        dwKills uint32
        dwDeaths uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdatePvp {
        dwKills: number;
        dwDeaths: number;
    }
    ```


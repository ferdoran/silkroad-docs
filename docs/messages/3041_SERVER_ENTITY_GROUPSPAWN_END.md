# SERVER_ENTITY_GROUPSPAWN_END
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3041` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00882280` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wCount` | `u16` | 2 | `0x0088228C` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] wCount                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityGroupspawnEnd {
        uint16_t wCount;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityGroupspawnEnd(
        ushort wCount
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityGroupspawnEnd {
        pub w_count: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityGroupspawnEnd struct {
        wCount uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityGroupspawnEnd {
        wCount: number;
    }
    ```


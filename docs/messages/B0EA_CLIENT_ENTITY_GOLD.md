# CLIENT_ENTITY_GOLD
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0EA` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881670` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0088167B` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityGold {
        uint32_t dwUniqueID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityGold(
        uint dwUniqueID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityGold {
        pub dw_unique_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityGold struct {
        dwUniqueID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityGold {
        dwUniqueID: number;
    }
    ```


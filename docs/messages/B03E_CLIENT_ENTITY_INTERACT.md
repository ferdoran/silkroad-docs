# CLIENT_ENTITY_INTERACT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB03E` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A78B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A78BF` |
| 2 | `byFlags` | `u8` | 1 | `0x008A78CD` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byFlags                        u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityInteract {
        uint32_t dwUniqueID;
        uint8_t byFlags;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityInteract(
        uint dwUniqueID,
        byte byFlags
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityInteract {
        pub dw_unique_id: u32,
        pub by_flags: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityInteract struct {
        dwUniqueID uint32
        byFlags uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityInteract {
        dwUniqueID: number;
        byFlags: number;
    }
    ```


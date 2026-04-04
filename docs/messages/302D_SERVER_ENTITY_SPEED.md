# SERVER_ENTITY_SPEED
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x302D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7950` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A795F` |
| 2 | `bySpeedType` | `u8` | 1 | `0x008A796D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] bySpeedType                    u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpeed {
        uint32_t dwUniqueID;
        uint8_t bySpeedType;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySpeed(
        uint dwUniqueID,
        byte bySpeedType
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpeed {
        pub dw_unique_id: u32,
        pub by_speed_type: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpeed struct {
        dwUniqueID uint32
        bySpeedType uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySpeed {
        dwUniqueID: number;
        bySpeedType: number;
    }
    ```


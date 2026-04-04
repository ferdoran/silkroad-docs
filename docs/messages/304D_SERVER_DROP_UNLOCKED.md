# SERVER_DROP_UNLOCKED

> Previously documented as `SERVER_ENTITY_UPDATE_STATUS` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x304D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880A70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUpdateType` | `u8` | 1 | `0x00880A7E` |
| 2 | `wValue` | `u16` | 2 | `0x00880A93` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byUpdateType                   u8
  [   1] wValue                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateStatus {
        uint8_t byUpdateType;
        uint16_t wValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateStatus(
        byte byUpdateType,
        ushort wValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateStatus {
        pub by_update_type: u8,
        pub w_value: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateStatus struct {
        byUpdateType uint8
        wValue uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateStatus {
        byUpdateType: number;
        wValue: number;
    }
    ```


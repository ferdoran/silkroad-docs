# SERVER_ENTITY_UPDATE_XP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3109` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00881E70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x00881E7E` |
| 2 | `wValue` | `u16` | 2 | `0x00881E98` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] wValue                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateXp {
        uint8_t byType;
        uint16_t wValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateXp(
        byte byType,
        ushort wValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateXp {
        pub by_type: u8,
        pub w_value: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateXp struct {
        byType uint8
        wValue uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateXp {
        byType: number;
        wValue: number;
    }
    ```


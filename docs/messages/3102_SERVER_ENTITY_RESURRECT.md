# SERVER_ENTITY_RESURRECT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3102` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00881DD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881DDE` |
| 2 | `wValue` | `u16` | 2 | `0x00881DF8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wValue                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityResurrect {
        uint8_t byResult;
        uint16_t wValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityResurrect(
        byte byResult,
        ushort wValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityResurrect {
        pub by_result: u8,
        pub w_value: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityResurrect struct {
        byResult uint8
        wValue uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityResurrect {
        byResult: number;
        wValue: number;
    }
    ```


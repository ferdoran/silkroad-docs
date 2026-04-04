# SERVER_ENTITY_UPDATE_GUILD
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3120` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088D700` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D70F` |
| 2 | `wValue` | `u16` | 2 | `0x0088D71D` |

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
    struct EntityUpdateGuild {
        uint8_t byResult;
        uint16_t wValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateGuild(
        byte byResult,
        ushort wValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateGuild {
        pub by_result: u8,
        pub w_value: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateGuild struct {
        byResult uint8
        wValue uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateGuild {
        byResult: number;
        wValue: number;
    }
    ```


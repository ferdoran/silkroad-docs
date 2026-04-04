# CLIENT_FORTRESS_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB462` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DEC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DECE` |
| 2 | `wLevel` | `u16` | 2 | `0x0088DF0D` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wLevel                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct FortressAction {
        uint8_t byResult;
        uint16_t wLevel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressAction(
        byte byResult,
        ushort wLevel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressAction {
        pub by_result: u8,
        pub w_level: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressAction struct {
        byResult uint8
        wLevel uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressAction {
        byResult: number;
        wLevel: number;
    }
    ```


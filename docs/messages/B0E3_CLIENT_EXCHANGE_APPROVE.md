# CLIENT_EXCHANGE_APPROVE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E3` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00889210` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00889223` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeApprove {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeApprove(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeApprove {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ExchangeApprove struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeApprove {
        byResult: number;
    }
    ```


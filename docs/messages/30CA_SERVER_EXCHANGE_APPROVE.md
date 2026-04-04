# SERVER_EXCHANGE_APPROVE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30CA` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7AC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7ACE` |
| 2 | `byFlag` | `u8` | 1 | `0x008A7AE9` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byFlag                         u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeApprove {
        uint8_t byResult;
        uint8_t byFlag;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeApprove(
        byte byResult,
        byte byFlag
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeApprove {
        pub by_result: u8,
        pub by_flag: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ExchangeApprove struct {
        byResult uint8
        byFlag uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeApprove {
        byResult: number;
        byFlag: number;
    }
    ```


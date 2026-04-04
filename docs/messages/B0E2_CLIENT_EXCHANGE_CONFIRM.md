# CLIENT_EXCHANGE_CONFIRM
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E2` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008890B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008890C1` |
| 2 | `byAction` | `u8` | 1 | `0x008890DE` |
| 3 | `byConfirm` | `u8` | 1 | `0x008890EC` |
| 4 | `dwParam` | `u32` | 4 | `0x008890FA` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] byConfirm                      u8
  [   3] dwParam                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeConfirm {
        uint8_t byResult;
        uint8_t byAction;
        uint8_t byConfirm;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeConfirm(
        byte byResult,
        byte byAction,
        byte byConfirm,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeConfirm {
        pub by_result: u8,
        pub by_action: u8,
        pub by_confirm: u8,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ExchangeConfirm struct {
        byResult uint8
        byAction uint8
        byConfirm uint8
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeConfirm {
        byResult: number;
        byAction: number;
        byConfirm: number;
        dwParam: number;
    }
    ```


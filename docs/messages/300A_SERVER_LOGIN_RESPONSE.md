# SERVER_LOGIN_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x300A` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0086DBD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0086DBDE` |
| 2 | `wErrorCode` | `u16` | 2 | `0x0086DC17` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct LoginResponse {
        uint8_t byResult;
        uint16_t wErrorCode;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record LoginResponse(
        byte byResult,
        ushort wErrorCode
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct LoginResponse {
        pub by_result: u8,
        pub w_error_code: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type LoginResponse struct {
        byResult uint8
        wErrorCode uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface LoginResponse {
        byResult: number;
        wErrorCode: number;
    }
    ```


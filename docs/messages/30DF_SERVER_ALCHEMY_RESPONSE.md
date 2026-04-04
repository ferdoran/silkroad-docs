# SERVER_ALCHEMY_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30DF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7550` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A755F` |
| 2 | `byType` | `u8` | 1 | `0x008A756D` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byType                         u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AlchemyResponse {
        uint8_t byResult;
        uint8_t byType;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AlchemyResponse(
        byte byResult,
        byte byType
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AlchemyResponse {
        pub by_result: u8,
        pub by_type: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type AlchemyResponse struct {
        byResult uint8
        byType uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AlchemyResponse {
        byResult: number;
        byType: number;
    }
    ```


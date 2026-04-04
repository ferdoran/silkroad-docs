# CLIENT_STALL_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB47A` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DF60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DF6B` |

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
    struct StallResponse {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallResponse(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallResponse {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallResponse struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallResponse {
        byResult: number;
    }
    ```


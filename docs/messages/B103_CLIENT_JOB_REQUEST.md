# CLIENT_JOB_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB103` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00881BD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881BDE` |

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
    struct JobRequest {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobRequest(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobRequest {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobRequest struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobRequest {
        byResult: number;
    }
    ```


# CLIENT_JOB_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB104` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00889680` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008896B0` |

**Total size**: 1 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_MLEAVE_SUCCESS` | UI |

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobAction {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobAction(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobAction {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobAction struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobAction {
        byResult: number;
    }
    ```


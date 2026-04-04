# SERVER_EVENT_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x34B1` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x008727A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008727AE` |

**Total size**: 1 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_TRANSITION_CANCEL_RESULT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EventAction {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EventAction(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EventAction {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EventAction struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EventAction {
        byResult: number;
    }
    ```


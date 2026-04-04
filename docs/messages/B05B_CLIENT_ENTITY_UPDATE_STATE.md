# CLIENT_ENTITY_UPDATE_STATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB05B` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881690` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008816A1` |
| 2 | `ullState` | `u64` | 8 | `0x008816C3` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] ullState                       u64
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateState {
        uint8_t byResult;
        uint64_t ullState;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateState(
        byte byResult,
        ulong ullState
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateState {
        pub by_result: u8,
        pub ull_state: u64,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateState struct {
        byResult uint8
        ullState uint64
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateState {
        byResult: number;
        ullState: bigint;
    }
    ```


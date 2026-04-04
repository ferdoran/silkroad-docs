# CLIENT_ARENA_STATUS
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB25A` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x0088D9C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D9CE` |
| 2 | `byStatus` | `u8` | 1 | `0x0088D9E4` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byStatus                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaStatus {
        uint8_t byResult;
        uint8_t byStatus;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaStatus(
        byte byResult,
        byte byStatus
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaStatus {
        pub by_result: u8,
        pub by_status: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaStatus struct {
        byResult uint8
        byStatus uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaStatus {
        byResult: number;
        byStatus: number;
    }
    ```


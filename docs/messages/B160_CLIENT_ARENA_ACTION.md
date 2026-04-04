# CLIENT_ARENA_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB160` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0089B660` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089B692` |
| 2 | `dwArenaID` | `u32` | 4 | `0x0089B6A8` |
| 3 | `dwParam` | `u32` | 4 | `0x0089B6B6` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwArenaID                      u32
  [   5] dwParam                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaAction {
        uint8_t byResult;
        uint32_t dwArenaID;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaAction(
        byte byResult,
        uint dwArenaID,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaAction {
        pub by_result: u8,
        pub dw_arena_id: u32,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaAction struct {
        byResult uint8
        dwArenaID uint32
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaAction {
        byResult: number;
        dwArenaID: number;
        dwParam: number;
    }
    ```


# CLIENT_ARENA_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB121` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0089F710` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTradeID` | `u32` | 4 | `0x0089F72F` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x0089F73D` |
| 3 | `byFlags` | `u8` | 1 | `0x0089F74B` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] dwTradeID                      u32
  [   4] dwTargetUID                    u32
  [   8] byFlags                        u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaRequest {
        uint32_t dwTradeID;
        uint32_t dwTargetUID;
        uint8_t byFlags;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaRequest(
        uint dwTradeID,
        uint dwTargetUID,
        byte byFlags
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaRequest {
        pub dw_trade_id: u32,
        pub dw_target_uid: u32,
        pub by_flags: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaRequest struct {
        dwTradeID uint32
        dwTargetUID uint32
        byFlags uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaRequest {
        dwTradeID: number;
        dwTargetUID: number;
        byFlags: number;
    }
    ```


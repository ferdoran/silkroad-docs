# CLIENT_STALL_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0D9` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881450` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088145E` |
| 2 | `dwAction` | `u32` | 4 | `0x00881474` |
| 3 | `wParam` | `u16` | 2 | `0x0088149C` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwAction                       u32
  [   5] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallUpdate {
        uint8_t byResult;
        uint32_t dwAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallUpdate(
        byte byResult,
        uint dwAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallUpdate {
        pub by_result: u8,
        pub dw_action: u32,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallUpdate struct {
        byResult uint8
        dwAction uint32
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallUpdate {
        byResult: number;
        dwAction: number;
        wParam: number;
    }
    ```


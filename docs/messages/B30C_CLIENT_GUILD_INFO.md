# CLIENT_GUILD_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB30C` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x0088D390` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D39E` |
| 2 | `wParam` | `u16` | 2 | `0x0088D3B3` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildInfo {
        uint8_t byResult;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildInfo(
        byte byResult,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildInfo {
        pub by_result: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildInfo struct {
        byResult uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildInfo {
        byResult: number;
        wParam: number;
    }
    ```


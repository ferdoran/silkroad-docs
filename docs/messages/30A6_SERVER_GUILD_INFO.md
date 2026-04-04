# SERVER_GUILD_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30A6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4DE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A4DF0` |
| 2 | `dwGuildID` | `u32` | 4 | `0x008A4E0F` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwGuildID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildInfo {
        uint8_t byResult;
        uint32_t dwGuildID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildInfo(
        byte byResult,
        uint dwGuildID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildInfo {
        pub by_result: u8,
        pub dw_guild_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildInfo struct {
        byResult uint8
        dwGuildID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildInfo {
        byResult: number;
        dwGuildID: number;
    }
    ```


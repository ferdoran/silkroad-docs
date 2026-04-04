# SERVER_GUILD_DATA_BEGIN

> **Corrected name** (server RE): Was `SERVER_EVENT_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B3` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x00881C60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881C6E` |
| 2 | `wField_02` | `u16` | 2 | `0x00881C88` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildDataBegin {
        uint8_t byResult;
        uint16_t wField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildDataBegin(
        byte byResult,
        ushort wField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildDataBegin {
        pub by_result: u8,
        pub w_field_02: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildDataBegin struct {
        byResult uint8
        wField_02 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildDataBegin {
        byResult: number;
        wField_02: number;
    }
    ```


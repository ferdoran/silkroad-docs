# SERVER_ENTITY_TALK_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_NPC_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB046` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00882E50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byOption1` | `u8` | 1 | `0x00882E75` |
| 2 | `byOption2` | `u8` | 1 | `0x00882E83` |
| 3 | `dwAction` | `u32` | 4 | `0x00882E91` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byOption1                      u8
  [   1] byOption2                      u8
  [   2] dwAction                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityTalkResponse {
        uint8_t byOption1;
        uint8_t byOption2;
        uint32_t dwAction;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityTalkResponse(
        byte byOption1,
        byte byOption2,
        uint dwAction
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityTalkResponse {
        pub by_option1: u8,
        pub by_option2: u8,
        pub dw_action: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityTalkResponse struct {
        byOption1 uint8
        byOption2 uint8
        dwAction uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityTalkResponse {
        byOption1: number;
        byOption2: number;
        dwAction: number;
    }
    ```


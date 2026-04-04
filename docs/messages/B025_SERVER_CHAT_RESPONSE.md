# SERVER_CHAT_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHARACTER_DELETE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB025` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872740` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwCharID` | `u32` | 4 | `0x0087274F` |
| 2 | `dwConfirm` | `u32` | 4 | `0x0087275D` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwCharID                       u32
  [   4] dwConfirm                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ChatResponse {
        uint32_t dwCharID;
        uint32_t dwConfirm;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ChatResponse(
        uint dwCharID,
        uint dwConfirm
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ChatResponse {
        pub dw_char_id: u32,
        pub dw_confirm: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ChatResponse struct {
        dwCharID uint32
        dwConfirm uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ChatResponse {
        dwCharID: number;
        dwConfirm: number;
    }
    ```


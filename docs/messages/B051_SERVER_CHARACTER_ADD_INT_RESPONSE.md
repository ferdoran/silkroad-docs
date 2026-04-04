# SERVER_CHARACTER_ADD_INT_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHAT_CLEAR` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB051` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880AC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880ACE` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterAddIntResponse {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterAddIntResponse(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterAddIntResponse {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterAddIntResponse struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterAddIntResponse {
        byResult: number;
    }
    ```


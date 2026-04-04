# SERVER_CHARACTER_ADD_STR_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHAT_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB050` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087FFD0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byChatType` | `bool` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byChatType` | `u8` | 1 | `0x0087FFDE` |
| 2 | `wMessageLen` | `u16` | 2 | `0x0087FFF8` |

**Total size**: 3 bytes

</details>
### Structure Summary

```
  [   0] byChatType                     u8
  [   1] wMessageLen                    u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterAddStrResponse {
        uint8_t byChatType;
        uint16_t wMessageLen;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterAddStrResponse(
        byte byChatType,
        ushort wMessageLen
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterAddStrResponse {
        pub by_chat_type: u8,
        pub w_message_len: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterAddStrResponse struct {
        byChatType uint8
        wMessageLen uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterAddStrResponse {
        byChatType: number;
        wMessageLen: number;
    }
    ```


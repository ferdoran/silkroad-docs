# SERVER_ENTITY_EMOTE_USE

> **Corrected name** (server RE): Was `SERVER_PARTY_INVITE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3091` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00877810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008778D8` |
| 2 | `wSenderLen` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesSender` | `bytes` | variable | `0x004F7AB9` |
| 4 | `dwPartyID` | `u32` | 4 | `0x008779E3` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wSenderLen                     u16
  [   3] bytesSender                    bytes  (variable length)
  [   0] dwPartyID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityEmoteUse {
        uint8_t byResult;
        uint16_t wSenderLen;
        std::vector<uint8_t> bytesSender;
        uint32_t dwPartyID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityEmoteUse(
        byte byResult,
        ushort wSenderLen,
        byte[] bytesSender,
        uint dwPartyID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityEmoteUse {
        pub by_result: u8,
        pub w_sender_len: u16,
        pub bytes_sender: Vec<u8>,
        pub dw_party_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityEmoteUse struct {
        byResult uint8
        wSenderLen uint16
        bytesSender []byte
        dwPartyID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityEmoteUse {
        byResult: number;
        wSenderLen: number;
        bytesSender: Uint8Array;
        dwPartyID: number;
    }
    ```


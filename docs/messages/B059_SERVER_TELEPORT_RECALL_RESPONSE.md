# SERVER_TELEPORT_RECALL_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_EMOTE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB059` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872590` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUnknown` | `bytes` | variable | `0x008725B3` |
| 2 | `byEmoteType` | `u8` | 1 | `0x008725C1` |
| 3 | `wEmoteID` | `u16` | 2 | `0x008725D8` |
| 4 | `dwTargetUID` | `u32` | 4 | `0x008725EA` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] byUnknown                      bytes  (variable length)
  [   0] byEmoteType                    u8
  [   1] wEmoteID                       u16
  [   3] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportRecallResponse {
        std::vector<uint8_t> byUnknown;
        uint8_t byEmoteType;
        uint16_t wEmoteID;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportRecallResponse(
        byte[] byUnknown,
        byte byEmoteType,
        ushort wEmoteID,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportRecallResponse {
        pub by_unknown: Vec<u8>,
        pub by_emote_type: u8,
        pub w_emote_id: u16,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportRecallResponse struct {
        byUnknown []byte
        byEmoteType uint8
        wEmoteID uint16
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportRecallResponse {
        byUnknown: Uint8Array;
        byEmoteType: number;
        wEmoteID: number;
        dwTargetUID: number;
    }
    ```


# SERVER_CHAT_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3055` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6F50` |

### Fields

No payload structure could be recovered from static analysis.

The opcode `0x3055` does not appear as a direct `PUSH` instruction in SR_GameServer.exe
or any of the analyzed plugin DLLs. Possible explanations:

- **Computed opcode**: The opcode may be derived at runtime (e.g. `base_opcode + index`)
  rather than hard-coded as an immediate constant.
- **Plugin or extension**: May be sent from a module not present in the analyzed binaries.
- **Rarely triggered path**: Could be guarded behind a feature flag not active in this build.

### Related Opcodes

| Opcode | Name | Notes |
|--------|------|-------|
| `0x3026` | `SERVER_CHAT_UPDATE` | Chat-domain message (10 code refs in binary) |
| `0x3055` | `SERVER_CHAT_UPDATE` (this) | Unknown structure |

### Investigation Status

Searched in: SR_GameServer.exe (clean), GatewayServer.exe, AgentServer.exe,
SR_ShardManager.exe, all SMPlugin DLLs — **no PUSH pattern found**.

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ChatUpdate {};  // no payload
    ```

=== "C#"
    ```csharp
    // C#
    public record ChatUpdate();  // no payload
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ChatUpdate;  // no payload
    ```

=== "Go"
    ```go
    // Go
    type ChatUpdate struct{}  // no payload
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ChatUpdate {}  // no payload
    ```


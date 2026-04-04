# CLIENT_ACADEMY_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB252` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x0088E690` |

### Fields

No payload structure could be recovered from static analysis of the server binaries.

The opcode `0xB252` does **not** appear as a `PUSH` instruction in SR_GameServer.exe —
confirming this is a **Client → Server** message received and dispatched by the server,
not one the server sends. The server's receive handler for this opcode is registered in
the `CCmdDispatcher` table at index `0xB252 & 0x7FF = 0x252`.

#### What is Known

The GatewayServer contains a Yahoo-based credential verification flow. The academy
(training camp) action uses a separate academy-specific protocol sub-system
(`3256_SERVER_ACADEMY_UPDATE.md`, `B250_SERVER_GUILD_STORAGE_RESPONSE.md`, etc.).

Possible field structure based on sibling academy messages:

| # | Name | Type | Description |
|---|------|------|-------------|
| 1 | `ActionType` | `u8` | Academy action type (join, leave, promote, etc.) |
| 2 | `TargetID` | `u32` | Target character or academy ID |

> These fields are inferred — not confirmed from binary analysis.

### Investigation Status

Searched in: SR_GameServer.exe (clean) — `PUSH 0xB252` **not found** (confirms
client→server direction). Server receive handler registered via `CCmdDispatcher`.

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyAction {};  // no payload
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyAction();  // no payload
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyAction;  // no payload
    ```

=== "Go"
    ```go
    // Go
    type AcademyAction struct{}  // no payload
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyAction {}  // no payload
    ```


# SERVER_GUILD_DATA_END

> **Corrected name** (server RE): Was `SERVER_EVENT_DATA` (client-derived).
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B4` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x00883060` |
| Send site | `0x004DFB7F` (SR_GameServer.exe clean) |
| Multi-part | Envelope: `0x34B3` BEGIN / `0x3101` DATA (repeated) / `0x34B4` END |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `updateType` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

**No payload.** This is the closing marker for the guild data multi-part stream.
The server sends it immediately after all `0x3101 SERVER_GUILD_DATA` packets.

</details>
### Protocol Context

| Packet | Role |
|--------|------|
| `0x34B3` `SERVER_GUILD_DATA_BEGIN` | Start marker |
| `0x3101` `SERVER_GUILD_DATA` | Guild + member data (repeated per guild) |
| `0x3102` | Guild extended data |
| `0x3109` | Additional guild info |
| `0x34B4` `SERVER_GUILD_DATA_END` | **End marker — no payload** |

### Binary Evidence

Disassembly at VA `0x4DFB7F` (SR_GameServer.exe clean):

```asm
004DFB76: mov  edx, [esi + 0x278]  ; vtable CreatePacket slot
004DFB7F: push 0x34B4              ; opcode
004DFB84: mov  ecx, ebp
004DFB86: call edx                 ; CreatePacket(0x34B4)
004DFB88: push eax                 ; packet handle
004DFB89: mov  eax, [esi + 0x27c]  ; vtable SendPacket slot
004DFB91: call eax                 ; SendPacket — no field writes between
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildDataEnd {};  // no payload
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildDataEnd();  // no payload
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildDataEnd;  // no payload
    ```

=== "Go"
    ```go
    // Go
    type GuildDataEnd struct{}  // no payload
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildDataEnd {}  // no payload
    ```


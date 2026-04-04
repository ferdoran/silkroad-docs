# SERVER_GUILD_STORAGE_DATA_END

> Previously documented as `SERVER_ACADEMY_DATA` (client-derived).

> **Corrected name** (server RE): Was `SERVER_ACADEMY_DATA` (client-derived). Binary analysis
> confirms this is the **end marker** for the guild storage data stream.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3254` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088EB10` |
| Send site | `0x004E1DCB` (SR_GameServer.exe clean) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unk` | `u8` | 1 |  |
| 2 | `itemsCount` | `u8` | 1 |  |
| 3 | `slot` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

**No payload.** This packet closes the guild storage data stream sent by
`0x3255 SERVER_GUILD_STORAGE_DATA`. The server creates and immediately sends it with
no field writes.

</details>
### Protocol Context

| Packet | Role |
|--------|------|
| `0x3253` | Guild storage open (1 field: item count) |
| `0x3255` `SERVER_GUILD_STORAGE_DATA` | Bulk item data (massive buffer per item) |
| `0x3254` `SERVER_GUILD_STORAGE_DATA_END` | **End marker — no payload** |

### Binary Evidence

Decompiled (`r2ghidra`, `fcn.004e1cb0`):

```c
// After sending the bulk buffer (fcn.004b8ad0 fills the item data):
iVar1 = *unaff_ESI;
uVar2 = (**(iVar1 + 0x278))(0x3254);   // CreatePacket(0x3254)
(**(iVar1 + 0x27c))(uVar2);             // SendPacket — no field writes
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildStorageDataEnd {};  // no payload
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildStorageDataEnd();  // no payload
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildStorageDataEnd;  // no payload
    ```

=== "Go"
    ```go
    // Go
    type GuildStorageDataEnd struct{}  // no payload
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildStorageDataEnd {}  // no payload
    ```


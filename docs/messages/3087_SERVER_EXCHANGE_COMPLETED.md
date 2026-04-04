# SERVER_EXCHANGE_COMPLETED

> Previously documented as `SERVER_INVENTORY_OPEN` (client-derived).

> **Corrected name** (server RE): Was `SERVER_INVENTORY_OPEN` (client-derived). The server
> function name and log strings confirm this is sent when a peer-to-peer trade is **completed**.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3087` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0087FCB0` |
| Send site | `0x004807AA` (SR_GameServer.exe clean) |

### Fields

**No payload.** This packet is sent to both trading parties when the exchange session
completes successfully. The packet carries no fields — the completion status is implicit
from the opcode.

Compare with `0x3088 SERVER_EXCHANGE_CANCELED` which carries a reason code.

### Protocol Context

| Packet | Trigger | Payload |
|--------|---------|---------|
| `0x3087` `SERVER_EXCHANGE_COMPLETED` | Trade confirmed by both sides | **none** |
| `0x3088` `SERVER_EXCHANGE_CANCELED` | Trade cancelled/timed-out | 1× WORD (reason) |

### Binary Evidence

Decompiled (`r2ghidra`, `fcn.004806d0`, trading session close handler):

```c
if (arg_10h == 1) {                               // condition: exchange completed
    uVar4 = (**(*piVar3 + 0x278))(0x3087);        // CreatePacket(0x3087)
    // no field writes
} else {
    uVar4 = (**(*piVar3 + 0x278))(0x3088);        // CreatePacket(0x3088)
    fcn.00404090(&arg_10h);                        // Write WORD reason code
}
(**(*piVar3 + 0x27c))(uVar4);                     // SendPacket
```

The packet is sent to both players in the trading session (`iVar7 < 2` loop).

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeCompleted {};  // no payload
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeCompleted();  // no payload
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeCompleted;  // no payload
    ```

=== "Go"
    ```go
    // Go
    type ExchangeCompleted struct{}  // no payload
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeCompleted {}  // no payload
    ```


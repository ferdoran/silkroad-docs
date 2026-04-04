# SERVER_TELEPORT_USE_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SIT_STAND` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB05A` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883520` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088355C` |
| 2 | `wNotifyID` | `u16` | 2 | `0x008835FD` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wNotifyID                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportUseResponse {
        uint8_t byResult;
        uint16_t wNotifyID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportUseResponse(
        byte byResult,
        ushort wNotifyID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportUseResponse {
        pub by_result: u8,
        pub w_notify_id: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportUseResponse struct {
        byResult uint8
        wNotifyID uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportUseResponse {
        byResult: number;
        wNotifyID: number;
    }
    ```


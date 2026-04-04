# SERVER_PARTY_MATCH_CREATION_RESPONSE

> Previously documented as `CLIENT_TELEPORT_CONFIRM` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB069` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880120` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088012F` |
| 2 | `dwPartyID` | `u32` | 4 | `0x00880172` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `OnJoinPartyAck[%d]` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwPartyID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportConfirm {
        uint8_t byResult;
        uint32_t dwPartyID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportConfirm(
        byte byResult,
        uint dwPartyID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportConfirm {
        pub by_result: u8,
        pub dw_party_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportConfirm struct {
        byResult uint8
        dwPartyID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportConfirm {
        byResult: number;
        dwPartyID: number;
    }
    ```


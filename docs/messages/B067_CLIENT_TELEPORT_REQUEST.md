# CLIENT_TELEPORT_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB067` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008800B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008800BF` |
| 2 | `wErrorCode` | `u16` | 2 | `0x008800F9` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `OnInvitePartymemberAck[%d]` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportRequest {
        uint8_t byResult;
        uint16_t wErrorCode;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportRequest(
        byte byResult,
        ushort wErrorCode
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportRequest {
        pub by_result: u8,
        pub w_error_code: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportRequest struct {
        byResult uint8
        wErrorCode uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportRequest {
        byResult: number;
        wErrorCode: number;
    }
    ```


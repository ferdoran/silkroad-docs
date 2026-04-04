# CLIENT_LOGIN_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB005` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0086DAB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wContentID` | `u16` | 2 | `0x0086DABF` |

**Total size**: 2 bytes

### String References
| String | Type |
|--------|------|
| `OnResetClient : %d` | Debug |
| `OnResetClient - End` | Debug |

### Structure Summary

```
  [   0] wContentID                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct LoginRequest {
        uint16_t wContentID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record LoginRequest(
        ushort wContentID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct LoginRequest {
        pub w_content_id: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type LoginRequest struct {
        wContentID uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface LoginRequest {
        wContentID: number;
    }
    ```


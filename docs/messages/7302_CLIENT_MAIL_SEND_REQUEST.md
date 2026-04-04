# CLIENT_MAIL_SEND_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

> **Corrected name** (server RE): Was `SERVER_PARTY_UPDATE` (client-derived). Direction: Client→Server (0x7xxx). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x7302` |
| Direction | Client → Server |
| Group | Chat Extended 3 |
| Handler(s) | `0x00881FD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881FDE` |
| 2 | `dwField_02` | `u32` | 4 | `0x00881FF4` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MailSendRequest {
        uint8_t byResult;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MailSendRequest(
        byte byResult,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MailSendRequest {
        pub by_result: u8,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type MailSendRequest struct {
        byResult uint8
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MailSendRequest {
        byResult: number;
        dwField_02: number;
    }
    ```


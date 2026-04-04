# SERVER_TELEPORT_READY_REQUEST

> **Corrected name** (server RE): Was `SERVER_EVENT_REWARD` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0086E5B0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `talkID` | `u8` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0086E600` |
| 2 | `dwField_02` | `u32` | 4 | `0x0086E60E` |

**Total size**: 5 bytes

</details>
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
    struct TeleportReadyRequest {
        uint8_t byResult;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportReadyRequest(
        byte byResult,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportReadyRequest {
        pub by_result: u8,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportReadyRequest struct {
        byResult uint8
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportReadyRequest {
        byResult: number;
        dwField_02: number;
    }
    ```


# SERVER_CHARACTER_ACTION_RESPONSE

> Previously documented as `CLIENT_ENTITY_INFO_REQUEST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB074` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008809D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008809DE` |
| 2 | `wParam` | `u16` | 2 | `0x008809F8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityInfoRequest {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityInfoRequest(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityInfoRequest {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityInfoRequest struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityInfoRequest {
        byAction: number;
        wParam: number;
    }
    ```


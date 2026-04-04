# CLIENT_ENTITY_SP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F6` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881A70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881A7E` |
| 2 | `wParam` | `u16` | 2 | `0x00881AB7` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_GUILD_COMMON_KNOW_REMIND_UPDATE` | UI |

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
    struct EntitySp {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySp(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySp {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySp struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySp {
        byAction: number;
        wParam: number;
    }
    ```


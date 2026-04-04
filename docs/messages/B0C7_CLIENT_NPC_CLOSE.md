# CLIENT_NPC_CLOSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0C7` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883B10` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00883B55` |

**Total size**: 1 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_COSERR_TOO_FAR_FROM_TRADECART` | UI |
| `UIIT_MSG_QUEST_ERR_TOO_FAR_FROM_MONSTER` | UI |

### Structure Summary

```
  [   0] byAction                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct NpcClose {
        uint8_t byAction;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record NpcClose(
        byte byAction
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct NpcClose {
        pub by_action: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type NpcClose struct {
        byAction uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface NpcClose {
        byAction: number;
    }
    ```


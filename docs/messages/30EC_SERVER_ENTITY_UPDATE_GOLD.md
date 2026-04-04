# SERVER_ENTITY_UPDATE_GOLD
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30EC` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008814B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008814BE` |
| 2 | `dwGold` | `u32` | 4 | `0x008814D4` |

**Total size**: 5 bytes

### Domain
quest

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_SR_ABORT_QUEST_ERROR_NOT_ALLOWED` | UI |
| `UIIT_STT_QUEST_GIVEUP_1` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwGold                         u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdateGold {
        uint8_t byAction;
        uint32_t dwGold;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdateGold(
        byte byAction,
        uint dwGold
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdateGold {
        pub by_action: u8,
        pub dw_gold: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdateGold struct {
        byAction uint8
        dwGold uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdateGold {
        byAction: number;
        dwGold: number;
    }
    ```


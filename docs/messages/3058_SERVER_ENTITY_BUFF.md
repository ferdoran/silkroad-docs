# SERVER_ENTITY_BUFF
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3058` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00872710` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087271B` |
| 2 | `dwBuffID` | `u32` | 4 | `0x0087274F` |
| 3 | `dwDuration` | `u32` | 4 | `0x0087275D` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwBuffID                       u32
  [   5] dwDuration                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityBuff {
        uint8_t byAction;
        uint32_t dwBuffID;
        uint32_t dwDuration;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityBuff(
        byte byAction,
        uint dwBuffID,
        uint dwDuration
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityBuff {
        pub by_action: u8,
        pub dw_buff_id: u32,
        pub dw_duration: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityBuff struct {
        byAction uint8
        dwBuffID uint32
        dwDuration uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityBuff {
        byAction: number;
        dwBuffID: number;
        dwDuration: number;
    }
    ```


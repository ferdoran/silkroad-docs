# SERVER_INVENTORY_ITEM_MOVEMENT

> **Corrected name** (server RE): Was `CLIENT_ENTITY_SELECT` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB034` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880DB0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `result` | `u8` | 1 |  |
| 2 | `type` | `u8` | 1 | if(result == 1) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00880DBE` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x00880DD9` |

**Total size**: 5 bytes

</details>
### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryItemMovement {
        uint8_t byAction;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryItemMovement(
        byte byAction,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryItemMovement {
        pub by_action: u8,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryItemMovement struct {
        byAction uint8
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryItemMovement {
        byAction: number;
        dwTargetUID: number;
    }
    ```


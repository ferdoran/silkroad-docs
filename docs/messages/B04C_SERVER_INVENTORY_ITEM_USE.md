# SERVER_INVENTORY_ITEM_USE

> **Corrected name** (server RE): Was `CLIENT_GAME_READY` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB04C` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A75C0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `slotInventory` | `u8` | 1 | if(packet.ReadBool() |
| 3 | `quantityUpdate` | `u16` | 2 | if(packet.ReadBool() |
| 4 | `usageType` | `u16` | 2 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A75CD` |

**Total size**: 4 bytes

</details>
### Structure Summary

```
  [   0] dwUniqueID                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryItemUse {
        uint32_t dwUniqueID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryItemUse(
        uint dwUniqueID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryItemUse {
        pub dw_unique_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryItemUse struct {
        dwUniqueID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryItemUse {
        dwUniqueID: number;
    }
    ```


# SERVER_INVENTORY_ITEM_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_GROUPSPAWN_START` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3040` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088BF30` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `slotInventory` | `u8` | 1 |  |
| 2 | `updateType` | `u8` | 1 |  |
| 3 | `quantity` | `u16` | 2 | case(8) |
| 4 | `StateType` | `u8` | 1 | case(8) → if(quantity == 0) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bySpawnType` | `u8` | 1 | `0x0088BF7F` |
| 2 | `byGroupType` | `u8` | 1 | `0x0088BF8D` |
| 3 | `dwGroupID` | `u32` | 4 | `0x0088C164` |
| 4 | `byEntityType` | `u8` | 1 | `0x0088C226` |
| 5 | `ullOwnerID` | `u64` | 8 | `0x0088C2D8` |
| 6 | `wCount` | `u16` | 2 | `0x0088C394` |
| 7 | `dwRefObjID` | `u32` | 4 | `0x0088C51E` |

**Total size**: 21 bytes

</details>
### Structure Summary

```
  [   0] bySpawnType                    u8
  [   1] byGroupType                    u8
  [   2] dwGroupID                      u32
  [   6] byEntityType                   u8
  [   7] ullOwnerID                     u64
  [  15] wCount                         u16
  [  17] dwRefObjID                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryItemUpdate {
        uint8_t bySpawnType;
        uint8_t byGroupType;
        uint32_t dwGroupID;
        uint8_t byEntityType;
        uint64_t ullOwnerID;
        uint16_t wCount;
        uint32_t dwRefObjID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryItemUpdate(
        byte bySpawnType,
        byte byGroupType,
        uint dwGroupID,
        byte byEntityType,
        ulong ullOwnerID,
        ushort wCount,
        uint dwRefObjID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryItemUpdate {
        pub by_spawn_type: u8,
        pub by_group_type: u8,
        pub dw_group_id: u32,
        pub by_entity_type: u8,
        pub ull_owner_id: u64,
        pub w_count: u16,
        pub dw_ref_obj_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryItemUpdate struct {
        bySpawnType uint8
        byGroupType uint8
        dwGroupID uint32
        byEntityType uint8
        ullOwnerID uint64
        wCount uint16
        dwRefObjID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryItemUpdate {
        bySpawnType: number;
        byGroupType: number;
        dwGroupID: number;
        byEntityType: number;
        ullOwnerID: bigint;
        wCount: number;
        dwRefObjID: number;
    }
    ```


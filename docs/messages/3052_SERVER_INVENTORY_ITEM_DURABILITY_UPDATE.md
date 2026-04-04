# SERVER_INVENTORY_ITEM_DURABILITY_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_MOVEMENT` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3052` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A70D0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `slotInventory` | `u8` | 1 |  |
| 2 | `durability` | `u32` | 4 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byMovementType` | `u8` | 1 | `0x008A70F7` |
| 2 | `ullTargetUID` | `u64` | 8 | `0x008A7124` |
| 3 | `byState` | `u8` | 1 | `0x008A7132` |
| 4 | `dwSpeed` | `u32` | 4 | `0x008A71E6` |
| 5 | `byDirection` | `u8` | 1 | `0x008A71F4` |
| 6 | `wRegionID` | `u16` | 2 | `0x008A72CF` |
| 7 | `byAngle` | `u8` | 1 | `0x008A72F3` |
| 8 | `dwPosX` | `u32` | 4 | `0x008A7301` |
| 9 | `dwPosZ` | `u32` | 4 | `0x008A7455` |

**Total size**: 26 bytes

</details>
### Structure Summary

```
  [   0] byMovementType                 u8
  [   1] ullTargetUID                   u64
  [   9] byState                        u8
  [  10] dwSpeed                        u32
  [  14] byDirection                    u8
  [  15] wRegionID                      u16
  [  17] byAngle                        u8
  [  18] dwPosX                         u32
  [  22] dwPosZ                         u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryItemDurabilityUpdate {
        uint8_t byMovementType;
        uint64_t ullTargetUID;
        uint8_t byState;
        uint32_t dwSpeed;
        uint8_t byDirection;
        uint16_t wRegionID;
        uint8_t byAngle;
        uint32_t dwPosX;
        uint32_t dwPosZ;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryItemDurabilityUpdate(
        byte byMovementType,
        ulong ullTargetUID,
        byte byState,
        uint dwSpeed,
        byte byDirection,
        ushort wRegionID,
        byte byAngle,
        uint dwPosX,
        uint dwPosZ
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryItemDurabilityUpdate {
        pub by_movement_type: u8,
        pub ull_target_uid: u64,
        pub by_state: u8,
        pub dw_speed: u32,
        pub by_direction: u8,
        pub w_region_id: u16,
        pub by_angle: u8,
        pub dw_pos_x: u32,
        pub dw_pos_z: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryItemDurabilityUpdate struct {
        byMovementType uint8
        ullTargetUID uint64
        byState uint8
        dwSpeed uint32
        byDirection uint8
        wRegionID uint16
        byAngle uint8
        dwPosX uint32
        dwPosZ uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryItemDurabilityUpdate {
        byMovementType: number;
        ullTargetUID: bigint;
        byState: number;
        dwSpeed: number;
        byDirection: number;
        wRegionID: number;
        byAngle: number;
        dwPosX: number;
        dwPosZ: number;
    }
    ```


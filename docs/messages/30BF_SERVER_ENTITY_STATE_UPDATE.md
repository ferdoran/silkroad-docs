# SERVER_ENTITY_STATE_UPDATE

> **Corrected name** (server RE): Was `SERVER_NPC_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30BF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6640` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Target entity |
| 2 | `UpdateType` | `u8` | 1 | State type being updated |
| 3 | `UpdateState` | `u8` | 1 | New state value |

**Total size**: 6 bytes

**UpdateType values:**

| UpdateType | State Enum | Values |
|------------|------------|--------|
| 0 | LifeState | `LIFESTATE_*` (Alive=0, Dead=1, etc.) |
| 1 | MotionState | `MOTIONSTATE_*` (Walking, Running, Sitting, etc.) |
| 4 | GameState | `BATTLESTATE_*` (Peace=0, Battle=1) |
| 7 | PVPState | `PvPSTATE_*` |
| 8 | InCombat | 0=false, 1=true |
| 11 | ScrollingType | Reverse return scroll, etc. |

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] UpdateType                     u8
  [   5] UpdateState                    u8
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x009A19AA` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x009A19B8` |
| 3 | `dwResponseType` | `u32` | 4 | `0x009A1AB6` |
| 4 | `dwParam` | `u32` | 4 | `0x009A1AC4` |
| 5 | `ullData` | `u64` | 8 | `0x009A1ADA` |
| 6 | `byNPCType` | `u8` | 1 | `0x009A1AE8` |
| 7 | `wDialogID` | `u16` | 2 | `0x009A1AF6` |
| 8 | `dwPriceRate` | `u32` | 4 | `0x009A1B69` |
| 9 | `byCanTrade` | `u8` | 1 | `0x009A1BB2` |
| 10 | `byCanStore` | `u8` | 1 | `0x009A1CB3` |
| 11 | `byCanRepair` | `u8` | 1 | `0x009A1CCE` |
| 12 | `dwGold` | `u32` | 4 | `0x009A1D12` |
| 13 | `bySpecialFlag` | `u8` | 1 | `0x009A1D41` |

> Note: Client handler data is from a different opcode's handler (NPC response — misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityStateUpdate {
        uint32_t UniqueID;
        uint8_t UpdateType;
        uint8_t UpdateState;
        uint32_t dwRefObjID;
        uint32_t dwUniqueID;
        uint32_t dwResponseType;
        uint32_t dwParam;
        uint64_t ullData;
        uint8_t byNPCType;
        uint16_t wDialogID;
        uint32_t dwPriceRate;
        uint8_t byCanTrade;
        uint8_t byCanStore;
        uint8_t byCanRepair;
        uint32_t dwGold;
        uint8_t bySpecialFlag;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStateUpdate(
        uint UniqueID,
        byte UpdateType,
        byte UpdateState,
        uint dwRefObjID,
        uint dwUniqueID,
        uint dwResponseType,
        uint dwParam,
        ulong ullData,
        byte byNPCType,
        ushort wDialogID,
        uint dwPriceRate,
        byte byCanTrade,
        byte byCanStore,
        byte byCanRepair,
        uint dwGold,
        byte bySpecialFlag
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStateUpdate {
        pub unique_id: u32,
        pub update_type: u8,
        pub update_state: u8,
        pub dw_ref_obj_id: u32,
        pub dw_unique_id: u32,
        pub dw_response_type: u32,
        pub dw_param: u32,
        pub ull_data: u64,
        pub by_npctype: u8,
        pub w_dialog_id: u16,
        pub dw_price_rate: u32,
        pub by_can_trade: u8,
        pub by_can_store: u8,
        pub by_can_repair: u8,
        pub dw_gold: u32,
        pub by_special_flag: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStateUpdate struct {
        UniqueID uint32
        UpdateType uint8
        UpdateState uint8
        dwRefObjID uint32
        dwUniqueID uint32
        dwResponseType uint32
        dwParam uint32
        ullData uint64
        byNPCType uint8
        wDialogID uint16
        dwPriceRate uint32
        byCanTrade uint8
        byCanStore uint8
        byCanRepair uint8
        dwGold uint32
        bySpecialFlag uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStateUpdate {
        uniqueID: number;
        updateType: number;
        updateState: number;
        dwRefObjID: number;
        dwUniqueID: number;
        dwResponseType: number;
        dwParam: number;
        ullData: bigint;
        byNPCType: number;
        wDialogID: number;
        dwPriceRate: number;
        byCanTrade: number;
        byCanStore: number;
        byCanRepair: number;
        dwGold: number;
        bySpecialFlag: number;
    }
    ```


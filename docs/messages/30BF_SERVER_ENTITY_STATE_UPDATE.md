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

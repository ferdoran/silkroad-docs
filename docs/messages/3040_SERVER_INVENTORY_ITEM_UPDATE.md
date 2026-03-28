# SERVER_INVENTORY_ITEM_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_GROUPSPAWN_START` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3040` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088BF30` |

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

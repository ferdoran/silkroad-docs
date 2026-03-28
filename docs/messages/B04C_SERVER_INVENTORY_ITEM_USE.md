# SERVER_INVENTORY_ITEM_USE

> **Corrected name** (server RE): Was `CLIENT_GAME_READY` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB04C` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A75C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A75CD` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
```

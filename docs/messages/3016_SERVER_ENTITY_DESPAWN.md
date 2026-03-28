# SERVER_ENTITY_DESPAWN

> **Corrected name** (server RE): Was `SERVER_CHARACTER_RESTORE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3016` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6CA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A6BE2` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A6C00` |
| 3 | `dwRealTime` | `u32` | 4 | `0x008A6C41` |
| 4 | `wDay` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wRegionID                      u16
  [   6] dwRealTime                     u32
  [  10] wDay                           u16
```

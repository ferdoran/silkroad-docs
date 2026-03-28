# SERVER_STORAGE_DATA_BEGIN

> **Corrected name** (server RE): Was `SERVER_ENTITY_UPDATE_POSITION` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3047` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008AC3D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A6D32` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A6D48` |
| 3 | `dwPosX` | `u32` | 4 | `0x008A6BE2` |
| 4 | `wAngle` | `u16` | 2 | `0x008A6C00` |
| 5 | `dwPosZ` | `u32` | 4 | `0x008A6C41` |
| 6 | `wDestRegion` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 15 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wRegionID                      u16
  [   3] dwPosX                         u32
  [   7] wAngle                         u16
  [   9] dwPosZ                         u32
  [  13] wDestRegion                    u16
```

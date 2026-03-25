# SERVER_ENTITY_UPDATE_EXP

| Property | Value |
|----------|-------|
| Opcode | `0x3076` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6CC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A6CCC` |
| 2 | `byUpdateType` | `u8` | 1 | `0x008A6D32` |
| 3 | `wRegionID` | `u16` | 2 | `0x008A6D48` |
| 4 | `dwRealTime` | `u32` | 4 | `0x008A6BE2` |
| 5 | `wDay` | `u16` | 2 | `0x008A6C00` |
| 6 | `dwParam1` | `u32` | 4 | `0x008A6C41` |
| 7 | `wParam2` | `u16` | 2 | `0x008A6C4F` |

**Total size**: 19 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byUpdateType                   u8
  [   5] wRegionID                      u16
  [   7] dwRealTime                     u32
  [  11] wDay                           u16
  [  13] dwParam1                       u32
  [  17] wParam2                        u16
```

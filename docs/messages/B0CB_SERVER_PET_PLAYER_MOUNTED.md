# SERVER_PET_PLAYER_MOUNTED

> **Corrected name** (server RE): Was `CLIENT_QUEST_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0CB` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A80A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A80B1` |
| 2 | `byAction` | `u8` | 1 | `0x008A80BF` |
| 3 | `byQuestType` | `u8` | 1 | `0x008A80CD` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] byQuestType                    u8
```

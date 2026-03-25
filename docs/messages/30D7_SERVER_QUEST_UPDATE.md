# SERVER_QUEST_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x30D7` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008811E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesQuestData` | `bytes` | variable | `0x00881208` |
| 2 | `byQuestType` | `u8` | 1 | `0x00881216` |
| 3 | `byQuestFlag` | `u8` | 1 | `0x00881224` |
| 4 | `wQuestID` | `u16` | 2 | `0x00881232` |
| 5 | `bytesRewardData` | `bytes[12]` | 12 | `0x00881240` |
| 6 | `dwQuestRefID` | `u32` | 4 | `0x00881255` |

**Minimum size**: 20 bytes + variable fields

### Structure Summary

```
  [   0] bytesQuestData                 bytes  (variable length)
  [   0] byQuestType                    u8
  [   1] byQuestFlag                    u8
  [   2] wQuestID                       u16
  [   4] bytesRewardData                bytes[12]
  [  16] dwQuestRefID                   u32
```

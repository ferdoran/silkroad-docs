# SERVER_QUEST_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30D6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008743A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byQuestAction` | `u8` | 1 | `0x008743DE` |
| 2 | `wQuestCount` | `u16` | 2 | `0x008743F8` |
| 3 | `wQuestIDLen` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesQuestIDs` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwParam1` | `u32` | 4 | `0x008744AD` |
| 6 | `dwParam2` | `u32` | 4 | `0x008744BB` |
| 7 | `dwParam3` | `u32` | 4 | `0x008744C9` |
| 8 | `wObjective1` | `u16` | 2 | `0x00874616` |
| 9 | `wObjective2` | `u16` | 2 | `0x00874681` |
| 10 | `wObjective3` | `u16` | 2 | `0x00874746` |

**Minimum size**: 23 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `%s -> *%s` | Debug |
| `SiegeManager MSG Result - Fail.` | Debug |
| `Trigger Action MSG Result - Fail.` | Debug |
| `Player:%d, NPC_Mob:%d, DroppedItem:%d` | Debug |
| `-> %s` | Debug |
| `SiegeManager MSG Result - Ok.` | Debug |
| `UIIT_STT_COSNEWUI_TITLE` | UI |

### Structure Summary

```
  [   0] byQuestAction                  u8
  [   1] wQuestCount                    u16
  [   3] wQuestIDLen                    u16
  [   5] bytesQuestIDs                  bytes  (variable length)
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
  [   8] dwParam3                       u32
  [  12] wObjective1                    u16
  [  14] wObjective2                    u16
  [  16] wObjective3                    u16
```

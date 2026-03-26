# SERVER_ENTITY_UPDATE_GOLD

| Property | Value |
|----------|-------|
| Opcode | `0x30EC` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008814B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008814BE` |
| 2 | `dwGold` | `u32` | 4 | `0x008814D4` |

**Total size**: 5 bytes


### Domain
quest

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_SR_ABORT_QUEST_ERROR_NOT_ALLOWED` | UI |
| `UIIT_STT_QUEST_GIVEUP_1` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwGold                         u32
```

# SERVER_EVENT_REWARD

| Property | Value |
|----------|-------|
| Opcode | `0x34B5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0086E5B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0086E600` |
| 2 | `dwField_02` | `u32` | 4 | `0x0086E60E` |

**Total size**: 5 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_STT_LETTER_FORENOON` | UI |
| `UIIT_STT_LETTER_AFTEMOON` | UI |
| `UIIT_MSG_GM_PUNISHMENT_CHAT_BLOCK` | UI |
| `UIIT_MSG_GM_PUNISHMENT_TRADE_BLOCK` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

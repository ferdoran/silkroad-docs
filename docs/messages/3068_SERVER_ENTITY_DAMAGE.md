# SERVER_ENTITY_DAMAGE

| Property | Value |
|----------|-------|
| Opcode | `0x3068` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0087A7B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byDamageType` | `u8` | 1 | `0x0087A7FB` |
| 2 | `byAttackType` | `u8` | 1 | `0x0087A833` |
| 3 | `wDamage` | `u16` | 2 | `0x0087A841` |
| 4 | `wAbsorbed` | `u16` | 2 | `0x0087A84F` |

**Total size**: 6 bytes


### String References
| String | Type |
|--------|------|
| `prim\\snd\\ui\\eventcomplete1.wav` | Debug |
| `ITEM_ETC_UNION_CREST_USER` | Debug |
| `ITEM_ETC_UNION_CREST_DELETE` | Debug |
| `UIIT_MSG_NASRUN_AWAKE_RENEW` | UI |
| `UIIT_STT_CONFIRM_BOX` | UI |
| `UIIT_MSG_GUILD_RECALL_CONFIRM` | UI |
| `UIIT_MSG_UNION_CREST_DELETE_COMPLETE` | UI |
| `UIIT_MSG_GUILD_CREST_DELETE_COMPLETE` | UI |
| `UIIT_MSG_ITEMB_STSTALL_CHAINGE` | UI |

### Structure Summary

```
  [   0] byDamageType                   u8
  [   1] byAttackType                   u8
  [   2] wDamage                        u16
  [   4] wAbsorbed                      u16
```

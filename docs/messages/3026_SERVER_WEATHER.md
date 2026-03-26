# SERVER_WEATHER

| Property | Value |
|----------|-------|
| Opcode | `0x3026` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00877340` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0087738C` |
| 2 | `byIntensity` | `u8` | 1 | `0x008773A6` |
| 3 | `byWindDir` | `u8` | 1 | `0x008773B4` |
| 4 | `wDuration` | `u16` | 2 | `0x0087753F` |
| 5 | `bySpecial` | `u8` | 1 | `0x00877560` |
| 6 | `byRegionWeather` | `u8` | 1 | `0x0087756E` |

**Total size**: 7 bytes


### String References
| String | Type |
|--------|------|
| `Chatting Error : %d` | Debug |
| `UIIT_CHATERR_YOU_ARE_SQUELCHED` | UI |
| `UIIT_CHATERR_CANT_FIND_TARGET` | UI |
| `UIIT_CHATERR_INVALID_COMMAND` | UI |
| `UIIT_CHATERR_NOT_A_PARTY_MEMBER` | UI |
| `UIIT_CHATERR_ALLIANCE_PERMISSION_DENIED` | UI |
| `UIIT_MSG_GUILD_UNION_CHAT_LIMIT` | UI |

### Structure Summary

```
  [   0] byType                         u8
  [   1] byIntensity                    u8
  [   2] byWindDir                      u8
  [   3] wDuration                      u16
  [   5] bySpecial                      u8
  [   6] byRegionWeather                u8
```

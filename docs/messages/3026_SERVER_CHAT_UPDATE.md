# SERVER_CHAT_UPDATE

> **Corrected name** (server RE): Was `SERVER_WEATHER` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

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

### Structure Summary

```
  [   0] byType                         u8
  [   1] byIntensity                    u8
  [   2] byWindDir                      u8
  [   3] wDuration                      u16
  [   5] bySpecial                      u8
  [   6] byRegionWeather                u8
```

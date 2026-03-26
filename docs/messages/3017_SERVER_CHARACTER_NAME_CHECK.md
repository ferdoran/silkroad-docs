# SERVER_CHARACTER_NAME_CHECK

| Property | Value |
|----------|-------|
| Opcode | `0x3017` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6DC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRealTime` | `u32` | 4 | `0x008A6DD9` |
| 2 | `wDay` | `u16` | 2 | `0x008A6DE9` |
| 3 | `byHour` | `u8` | 1 | `0x008A6DF9` |
| 4 | `byMinute` | `u8` | 1 | `0x008A6E09` |

**Total size**: 8 bytes


### Source File(s)
- `NetProcessInObject.cpp`

### Assert Expressions
```
Fun_GetCfgGame()->m_LocalTime.InitTimer(pM->dwRealTime, pM->m_wDay, pM->m_byHour, pM->m_byMin, 0)
```

This message is actually a **Server Time Sync** message — the assert reveals it initializes the local game timer with server time values.

### String References
| String | Type |
|--------|------|
| `Fun_GetCfgGame()->m_LocalTime.InitTimer(pM->dwRealTime,pM->m_wDay,pM->m_byHour,pM->m_byMin,0)` | Debug |

### Structure Summary

```
  [   0] dwRealTime                     u32
  [   4] wDay                           u16
  [   6] byHour                         u8
  [   7] byMinute                       u8
```

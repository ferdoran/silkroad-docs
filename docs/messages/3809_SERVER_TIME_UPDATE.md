# SERVER_TIME_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x3809` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x008A6E80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wDay` | `u16` | 2 | `0x008A6E9E` |
| 2 | `byHour` | `u8` | 1 | `0x008A6EAE` |
| 3 | `byMinute` | `u8` | 1 | `0x008A6EBE` |

**Total size**: 4 bytes


### String References
| String | Type |
|--------|------|
| `Fun_GetCfgGame()->m_LocalTime.InitTimer(pM->dwRealTime,pM->m_wDay,pM->m_byHour,pM->m_byMin,0)` | Debug |

### Structure Summary

```
  [   0] wDay                           u16
  [   2] byHour                         u8
  [   3] byMinute                       u8
```

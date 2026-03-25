# SERVER_ENTITY_UPDATE_PVP

| Property | Value |
|----------|-------|
| Opcode | `0x3122` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0089BAE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwKills` | `u32` | 4 | `0x0089BB3A` |
| 2 | `dwDeaths` | `u32` | 4 | `0x0089BB48` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwKills                        u32
  [   4] dwDeaths                       u32
```

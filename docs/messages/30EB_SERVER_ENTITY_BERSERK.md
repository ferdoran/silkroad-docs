# SERVER_ENTITY_BERSERK

| Property | Value |
|----------|-------|
| Opcode | `0x30EB` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880B60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00880B70` |
| 2 | `byLevel` | `u8` | 1 | `0x00880B7E` |
| 3 | `wDuration` | `u16` | 2 | `0x00880BB5` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] byLevel                        u8
  [   2] wDuration                      u16
```

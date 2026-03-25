# SERVER_ENTITY_LEVEL_UP

| Property | Value |
|----------|-------|
| Opcode | `0x3077` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088E1C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088E1CE` |
| 2 | `wNewLevel` | `u16` | 2 | `0x0088E1E3` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wNewLevel                      u16
```

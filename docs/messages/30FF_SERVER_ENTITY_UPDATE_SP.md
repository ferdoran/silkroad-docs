# SERVER_ENTITY_UPDATE_SP

| Property | Value |
|----------|-------|
| Opcode | `0x30FF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00881950` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088195E` |
| 2 | `wSP` | `u16` | 2 | `0x00881985` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wSP                            u16
```

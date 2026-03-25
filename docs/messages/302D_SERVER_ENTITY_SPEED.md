# SERVER_ENTITY_SPEED

| Property | Value |
|----------|-------|
| Opcode | `0x302D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7950` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A795F` |
| 2 | `bySpeedType` | `u8` | 1 | `0x008A796D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] bySpeedType                    u8
```

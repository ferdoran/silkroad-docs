# SERVER_GUILD_INFO

| Property | Value |
|----------|-------|
| Opcode | `0x30A6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4DE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A4DF0` |
| 2 | `dwGuildID` | `u32` | 4 | `0x008A4E0F` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwGuildID                      u32
```

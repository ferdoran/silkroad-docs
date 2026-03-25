# SERVER_CHARACTER_LIST

| Property | Value |
|----------|-------|
| Opcode | `0x3011` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008726E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwCharCount` | `u32` | 4 | `0x008726EE` |
| 2 | `byListType` | `u8` | 1 | `0x008726FC` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwCharCount                    u32
  [   4] byListType                     u8
```

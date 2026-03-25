# SERVER_ALCHEMY_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x30DF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7550` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A755F` |
| 2 | `byType` | `u8` | 1 | `0x008A756D` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byType                         u8
```

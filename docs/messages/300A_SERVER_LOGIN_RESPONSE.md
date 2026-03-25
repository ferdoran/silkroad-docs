# SERVER_LOGIN_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x300A` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0086DBD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0086DBDE` |
| 2 | `wErrorCode` | `u16` | 2 | `0x0086DC17` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u16
```

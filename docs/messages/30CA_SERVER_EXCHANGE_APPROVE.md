# SERVER_EXCHANGE_APPROVE

| Property | Value |
|----------|-------|
| Opcode | `0x30CA` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7AC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7ACE` |
| 2 | `byFlag` | `u8` | 1 | `0x008A7AE9` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byFlag                         u8
```

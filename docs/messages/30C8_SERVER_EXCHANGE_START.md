# SERVER_EXCHANGE_START

| Property | Value |
|----------|-------|
| Opcode | `0x30C8` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7870` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A787F` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A782E` |
| 3 | `dwParam1` | `u32` | 4 | `0x008A783C` |
| 4 | `dwParam2` | `u32` | 4 | `0x008A784A` |
| 5 | `byFlag` | `u8` | 1 | `0x008A7858` |

**Total size**: 14 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwTargetUID                    u32
  [   5] dwParam1                       u32
  [   9] dwParam2                       u32
  [  13] byFlag                         u8
```

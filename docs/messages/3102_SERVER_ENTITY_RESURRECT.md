# SERVER_ENTITY_RESURRECT

| Property | Value |
|----------|-------|
| Opcode | `0x3102` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00881DD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881DDE` |
| 2 | `wValue` | `u16` | 2 | `0x00881DF8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wValue                         u16
```

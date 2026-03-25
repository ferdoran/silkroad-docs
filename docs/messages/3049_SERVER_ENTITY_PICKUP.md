# SERVER_ENTITY_PICKUP

| Property | Value |
|----------|-------|
| Opcode | `0x3049` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A74F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `ullTargetUID` | `u64` | 8 | `0x008A7525` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] ullTargetUID                   u64
```

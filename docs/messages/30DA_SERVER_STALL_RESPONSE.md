# SERVER_STALL_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x30DA` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088DAD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DADF` |
| 2 | `dwStallUID` | `u32` | 4 | `0x0088DB05` |
| 3 | `dwGold` | `u32` | 4 | `0x0088DB13` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwStallUID                     u32
  [   5] dwGold                         u32
```

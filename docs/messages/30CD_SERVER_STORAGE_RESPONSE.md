# SERVER_STORAGE_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x30CD` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A763F` |
| 2 | `byResult` | `u8` | 1 | `0x008A764D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byResult                       u8
```

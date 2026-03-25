# SERVER_ENTITY_DESPAWN

| Property | Value |
|----------|-------|
| Opcode | `0x3042` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008822C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008822CF` |
| 2 | `byReason` | `u8` | 1 | `0x008822DD` |
| 3 | `byAnimation` | `u8` | 1 | `0x008822F9` |
| 4 | `byFlag` | `u8` | 1 | `0x00882313` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byReason                       u8
  [   5] byAnimation                    u8
  [   6] byFlag                         u8
```

# SERVER_ENTITY_BUFF

| Property | Value |
|----------|-------|
| Opcode | `0x3058` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00872710` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087271B` |
| 2 | `dwBuffID` | `u32` | 4 | `0x0087274F` |
| 3 | `dwDuration` | `u32` | 4 | `0x0087275D` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwBuffID                       u32
  [   5] dwDuration                     u32
```

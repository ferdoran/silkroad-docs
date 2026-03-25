# SERVER_ENTITY_UPDATE_XP

| Property | Value |
|----------|-------|
| Opcode | `0x3109` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00881E70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x00881E7E` |
| 2 | `wValue` | `u16` | 2 | `0x00881E98` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] wValue                         u16
```

# SERVER_CHAT_SYSTEM

| Property | Value |
|----------|-------|
| Opcode | `0x7030` |
| Direction | Server → Client |
| Group | Chat/Social |
| Handler(s) | `0x0088DA80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DA8E` |
| 2 | `wField_02` | `u16` | 2 | `0x0088DAA3` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

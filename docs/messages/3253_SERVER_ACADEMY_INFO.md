# SERVER_ACADEMY_INFO

| Property | Value |
|----------|-------|
| Opcode | `0x3253` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088D160` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D16E` |
| 2 | `bytesData_1` | `bytes` | variable | `0x00841948` |

**Minimum size**: 1 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
```

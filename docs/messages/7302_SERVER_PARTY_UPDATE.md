# SERVER_PARTY_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x7302` |
| Direction | Server → Client |
| Group | Chat Extended 3 |
| Handler(s) | `0x00881FD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881FDE` |
| 2 | `dwField_02` | `u32` | 4 | `0x00881FF4` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

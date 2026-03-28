# SERVER_TELEPORT_READY_REQUEST

> **Corrected name** (server RE): Was `SERVER_EVENT_REWARD` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0086E5B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0086E600` |
| 2 | `dwField_02` | `u32` | 4 | `0x0086E60E` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

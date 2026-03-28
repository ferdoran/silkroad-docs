# SERVER_ENTITY_SPEED_UPDATE

> **Corrected name** (server RE): Was `SERVER_PET_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30D0` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A51E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A51EE` |
| 2 | `wPetUID` | `u16` | 2 | `0x008A5203` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wPetUID                        u16
```

# SERVER_ENTITY_STATUS_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_ACTION` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3057` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008ADF50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byActionType` | `u8` | 1 | `0x008ADF9A` |
| 2 | `dwActionID` | `u32` | 4 | `0x008ADFA8` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byActionType                   u8
  [   1] dwActionID                     u32
```

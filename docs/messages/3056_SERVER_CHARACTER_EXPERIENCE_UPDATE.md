# SERVER_CHARACTER_EXPERIENCE_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_UPDATE_MOVEMENT` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3056` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7020` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A702D` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
```

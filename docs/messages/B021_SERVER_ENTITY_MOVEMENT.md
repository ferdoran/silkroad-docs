# SERVER_ENTITY_MOVEMENT

> **Corrected name** (server RE): Was `CLIENT_CHARACTER_CREATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB021` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872010` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087201B` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

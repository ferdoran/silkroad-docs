# SERVER_ENTITY_TALK_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_NPC_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB046` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00882E50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byOption1` | `u8` | 1 | `0x00882E75` |
| 2 | `byOption2` | `u8` | 1 | `0x00882E83` |
| 3 | `dwAction` | `u32` | 4 | `0x00882E91` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byOption1                      u8
  [   1] byOption2                      u8
  [   2] dwAction                       u32
```

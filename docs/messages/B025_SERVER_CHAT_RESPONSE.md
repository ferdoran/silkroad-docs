# SERVER_CHAT_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHARACTER_DELETE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB025` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872740` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwCharID` | `u32` | 4 | `0x0087274F` |
| 2 | `dwConfirm` | `u32` | 4 | `0x0087275D` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwCharID                       u32
  [   4] dwConfirm                      u32
```

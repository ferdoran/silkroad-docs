# SERVER_ENTITY_SKILL_BUFF_ADDED

> **Corrected name** (server RE): Was `CLIENT_STORAGE_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0BD` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A4960` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00A56691` |
| 2 | `wField_02` | `u16` | 2 | `0x00A566A8` |
| 3 | `dwField_03` | `u32` | 4 | `0x00A566B6` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] dwField_03                     u32
```

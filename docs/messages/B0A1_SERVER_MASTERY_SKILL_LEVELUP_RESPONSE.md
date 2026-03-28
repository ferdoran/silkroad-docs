# SERVER_MASTERY_SKILL_LEVELUP_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SKILL_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0A1` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A5360` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A5374` |
| 2 | `dwSkillID` | `u32` | 4 | `0x008A53A0` |
| 3 | `dwTargetUID` | `u32` | 4 | `0x008A53AE` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwSkillID                      u32
  [   5] dwTargetUID                    u32
```

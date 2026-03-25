# CLIENT_SKILL_USE

| Property | Value |
|----------|-------|
| Opcode | `0xB0A2` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880BE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880BEE` |
| 2 | `dwSkillID` | `u32` | 4 | `0x00880C08` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwSkillID                      u32
```

# CLIENT_SKILL_REQUEST

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


### String References
| String | Type |
|--------|------|
| `OnRefreshBuffRemaintime:%d` | Debug |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwSkillID                      u32
  [   5] dwTargetUID                    u32
```

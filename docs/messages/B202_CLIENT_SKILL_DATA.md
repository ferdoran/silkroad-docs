# CLIENT_SKILL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB202` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x00880E90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880E9F` |
| 2 | `dwMasteryID` | `u32` | 4 | `0x00880EB9` |
| 3 | `byAction` | `u8` | 1 | `0x00880EC7` |

**Total size**: 6 bytes


### Source File(s)
- `NetProcessInInterface.cpp`

### Assert Expressions
```
m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)
```

### String References
| String | Type |
|--------|------|
| `m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwMasteryID                    u32
  [   5] byAction                       u8
```

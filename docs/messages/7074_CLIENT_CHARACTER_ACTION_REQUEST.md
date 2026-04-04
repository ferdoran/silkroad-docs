# CLIENT_CHARACTER_ACTION_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0x7074` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unk` | `u8` | 1 |  |
| 2 | `SkillRemove` | `u8` | 1 |  |
| 3 | `skillID` | `u32` | 4 |  |
| 4 | `targetUniqueID` | `u32` | 4 |  |
| 5 | `unk` | `u8` | 1 |  |


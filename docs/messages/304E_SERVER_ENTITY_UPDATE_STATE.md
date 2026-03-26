# SERVER_ENTITY_UPDATE_STATE

| Property | Value |
|----------|-------|
| Opcode | `0x304E` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A97C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A980B` |
| 2 | `ullState1` | `u64` | 8 | `0x008A9819` |
| 3 | `ullState2` | `u64` | 8 | `0x008A9827` |
| 4 | `byFlag` | `u8` | 1 | `0x008A9835` |
| 5 | `dwParam1` | `u32` | 4 | `0x008A9851` |
| 6 | `dwParam2` | `u32` | 4 | `0x008A987C` |
| 7 | `dwParam3` | `u32` | 4 | `0x008A988A` |
| 8 | `wParam4` | `u16` | 2 | `0x008A997D` |

**Total size**: 35 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_STATE_GAIN_EXP` | UI |
| `UIIT_MSG_STATE_GET_SKILL_EXP` | UI |

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] ullState1                      u64
  [  12] ullState2                      u64
  [  20] byFlag                         u8
  [  21] dwParam1                       u32
  [  25] dwParam2                       u32
  [  29] dwParam3                       u32
  [  33] wParam4                        u16
```

# SERVER_ENTITY_NAME

| Property | Value |
|----------|-------|
| Opcode | `0x305C` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00873990` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesOldName` | `bytes` | variable | `0x008739F6` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x00873A04` |
| 3 | `bytesNewName` | `bytes` | variable | `0x00873A82` |
| 4 | `wRegionID` | `u16` | 2 | `0x00873AE8` |
| 5 | `byFlag` | `u8` | 1 | `0x00873AFC` |

**Minimum size**: 7 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_STATE_GET_ITEM_EXPENDABLE` | UI |
| `UIIT_MSG_PARTYGET_ITEM_EXPENDABLE` | UI |
| `UIIT_MSG_PARTYGET_GOLD` | UI |

### Structure Summary

```
  [   0] bytesOldName                   bytes  (variable length)
  [   0] dwUniqueID                     u32
  [   4] bytesNewName                   bytes  (variable length)
  [   0] wRegionID                      u16
  [   2] byFlag                         u8
```

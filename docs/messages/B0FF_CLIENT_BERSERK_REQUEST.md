# CLIENT_BERSERK_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0FF` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00892C50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00892C80` |
| 2 | `byAction` | `u8` | 1 | `0x00892C9C` |
| 3 | `wParam` | `u16` | 2 | `0x00892D41` |

**Total size**: 4 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_COMPLETE` | UI |
| `UIIT_MSG_TC_JOIN_CANCEL` | UI |
| `UIIT_MSG_TC_JOIN_NOREPLY` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] wParam                         u16
```

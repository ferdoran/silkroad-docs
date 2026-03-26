# CLIENT_BATTLE_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB516` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x00891080` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008910C8` |
| 2 | `byField_02` | `u8` | 1 | `0x008910FB` |
| 3 | `byField_03` | `u8` | 1 | `0x00891109` |
| 4 | `byField_04` | `u8` | 1 | `0x00891117` |
| 5 | `byField_05` | `u8` | 1 | `0x008911CB` |

**Total size**: 5 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_SAFETRADE_PROGRESS` | UI |
| `UIIT_MSG_SAFETRADE_NUMBER_ERR_LIMIT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] byField_05                     u8
```

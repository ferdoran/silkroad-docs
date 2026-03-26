# CLIENT_JOB_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB106` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x008857B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008857DF` |
| 2 | `wErrorCode` | `u16` | 2 | `0x00885860` |

**Total size**: 3 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_MRELEASE_VOTING` | UI |
| `UIIT_MSG_MRELEASEERR_NOTVOTETIME` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u16
```

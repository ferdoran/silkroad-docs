# SERVER_GLOBAL_CHAT

| Property | Value |
|----------|-------|
| Opcode | `0x3103` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088FD00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesMessage` | `bytes` | variable | `0x0088FD4F` |
| 2 | `dwParam1` | `u32` | 4 | `0x0088FD67` |
| 3 | `dwParam2` | `u32` | 4 | `0x0088FD75` |
| 4 | `bytesExtra` | `bytes` | variable | `0x0088FD82` |
| 5 | `wChannel` | `u16` | 2 | `0x00890174` |

**Minimum size**: 10 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_FORT_GUILD_COMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_SUBCOMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_BATTLEMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_PRODUCTMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_TRAINERMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_ENGINEER` | UI |
| `UIIT_MSG_FORT_POSITION_REMOVE_COMPLETE` | UI |
| `UIIT_MSG_FORT_POSITION_GRANT_COMPLETE` | UI |
| `UIIT_STT_CONFIRM_BOX` | UI |

### Structure Summary

```
  [   0] bytesMessage                   bytes  (variable length)
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
  [   8] bytesExtra                     bytes  (variable length)
  [   0] wChannel                       u16
```

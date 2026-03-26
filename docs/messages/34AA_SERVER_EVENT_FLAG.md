# SERVER_EVENT_FLAG

| Property | Value |
|----------|-------|
| Opcode | `0x34AA` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x008999B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x008999C2` |
| 2 | `byField_02` | `u8` | 1 | `0x008999D0` |
| 3 | `byField_03` | `u8` | 1 | `0x008999DE` |

**Total size**: 4 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_VIETNAM_MRSYSTEM_100` | UI |
| `UIIT_MSG_VIETNAM_MRSYSTEM_50` | UI |
| `UIIT_MSG_VIETNAM_MRSYSTEM_0` | UI |

### Structure Summary

```
  [   0] wParam                         u16
  [   2] byField_02                     u8
  [   3] byField_03                     u8
```

# SERVER_MAP_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x385F` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x00890210` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089027E` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |
| 4 | `byField_04` | `u8` | 1 | `0x0089029B` |

**Minimum size**: 7 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_FORT_GUILD_COMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_SUBCOMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_BATTLEMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_PRODUCTMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_TRAINERMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_ENGINEER` | UI |

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
  [   0] byField_04                     u8
```

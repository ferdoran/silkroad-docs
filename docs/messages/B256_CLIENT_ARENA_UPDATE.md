# CLIENT_ARENA_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB256` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x00895530` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089557B` |
| 2 | `byAction` | `u8` | 1 | `0x00895595` |
| 3 | `wItemID` | `u16` | 2 | `0x004F7A7D` |
| 4 | `wExtraParam` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x00895625` |
| 6 | `wField_06` | `u16` | 2 | `0x008957A2` |

**Minimum size**: 8 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] wItemID                        u16
  [   4] wExtraParam                    bytes  (variable length)
  [   0] wField_05                      u16
  [   2] wField_06                      u16
```

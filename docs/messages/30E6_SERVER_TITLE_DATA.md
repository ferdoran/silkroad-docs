# SERVER_TITLE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30E6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008ABCC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wTitleLen` | `u16` | 2 | `0x004F7A7D` |
| 2 | `bytesTitleName` | `bytes` | variable | `0x004F7AB9` |
| 3 | `dwTitleID` | `u32` | 4 | `0x008ABD22` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] wTitleLen                      u16
  [   2] bytesTitleName                 bytes  (variable length)
  [   0] dwTitleID                      u32
```

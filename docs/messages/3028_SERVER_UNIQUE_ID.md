# SERVER_UNIQUE_ID

| Property | Value |
|----------|-------|
| Opcode | `0x3028` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4F80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A4F92` |
| 2 | `wRegionID` | `u16` | 2 | `0x008A4FA0` |
| 3 | `bytesData` | `bytes[14]` | 14 | `0x008A4FAE` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wRegionID                      u16
  [   6] bytesData                      bytes[14]
```

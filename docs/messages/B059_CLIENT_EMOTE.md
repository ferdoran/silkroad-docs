# CLIENT_EMOTE

| Property | Value |
|----------|-------|
| Opcode | `0xB059` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872590` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x008725B3` |
| 2 | `byField_02` | `u8` | 1 | `0x008725C1` |
| 3 | `wField_03` | `u16` | 2 | `0x008725D8` |
| 4 | `dwField_04` | `u32` | 4 | `0x008725EA` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] byField_02                     u8
  [   1] wField_03                      u16
  [   3] dwField_04                     u32
```

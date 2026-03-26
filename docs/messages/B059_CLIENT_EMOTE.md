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
| 1 | `byUnknown` | `bytes` | variable | `0x008725B3` |
| 2 | `byEmoteType` | `u8` | 1 | `0x008725C1` |
| 3 | `wEmoteID` | `u16` | 2 | `0x008725D8` |
| 4 | `dwTargetUID` | `u32` | 4 | `0x008725EA` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] byUnknown                      bytes  (variable length)
  [   0] byEmoteType                    u8
  [   1] wEmoteID                       u16
  [   3] dwTargetUID                    u32
```

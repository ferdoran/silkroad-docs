# SERVER_ENTITY_LEVEL_UP

> **Corrected name** (server RE): Was `SERVER_CHAT_MESSAGE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3054` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00889D90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byChatType` | `u8` | 1 | `0x00889DFD` |
| 2 | `wSenderLen` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesSender` | `bytes` | variable | `0x004F7AB9` |
| 4 | `byFlag` | `u8` | 1 | `0x00889E80` |
| 5 | `dwParam` | `u32` | 4 | `0x00889FAD` |

**Minimum size**: 8 bytes + variable fields

### Structure Summary

```
  [   0] byChatType                     u8
  [   1] wSenderLen                     u16
  [   3] bytesSender                    bytes  (variable length)
  [   0] byFlag                         u8
  [   1] dwParam                        u32
```

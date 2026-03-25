# SERVER_PARTY_INVITE

| Property | Value |
|----------|-------|
| Opcode | `0x3091` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00877810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008778D8` |
| 2 | `wSenderLen` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesSender` | `bytes` | variable | `0x004F7AB9` |
| 4 | `dwPartyID` | `u32` | 4 | `0x008779E3` |

**Minimum size**: 7 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wSenderLen                     u16
  [   3] bytesSender                    bytes  (variable length)
  [   0] dwPartyID                      u32
```

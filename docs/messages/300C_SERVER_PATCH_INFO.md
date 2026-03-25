# SERVER_PATCH_INFO

| Property | Value |
|----------|-------|
| Opcode | `0x300C` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0086E100` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesPatchData` | `bytes` | variable | `0x008416B1` |
| 2 | `bytesUrl` | `bytes` | variable | `0x00841948` |
| 3 | `wVersion` | `u16` | 2 | `0x0086DABF` |

**Minimum size**: 2 bytes + variable fields

### Structure Summary

```
  [   0] bytesPatchData                 bytes  (variable length)
  [   0] bytesUrl                       bytes  (variable length)
  [   0] wVersion                       u16
```

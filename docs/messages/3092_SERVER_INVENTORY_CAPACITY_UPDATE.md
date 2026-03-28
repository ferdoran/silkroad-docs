# SERVER_INVENTORY_CAPACITY_UPDATE

> **Corrected name** (server RE): Was `SERVER_PARTY_INFO` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3092` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A8EA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A8ED2` |
| 2 | `wMemberCount` | `u16` | 2 | `0x008A8EEB` |
| 3 | `bytesMemberData` | `bytes` | variable | `0x008416B1` |
| 4 | `bytesPartyData` | `bytes` | variable | `0x00841948` |

**Minimum size**: 3 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wMemberCount                   u16
  [   3] bytesMemberData                bytes  (variable length)
  [   0] bytesPartyData                 bytes  (variable length)
```

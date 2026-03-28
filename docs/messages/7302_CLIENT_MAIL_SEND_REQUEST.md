# CLIENT_MAIL_SEND_REQUEST

> **Corrected name** (server RE): Was `SERVER_PARTY_UPDATE` (client-derived). Direction: Client→Server (0x7xxx). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x7302` |
| Direction | Client → Server |
| Group | Chat Extended 3 |
| Handler(s) | `0x00881FD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881FDE` |
| 2 | `dwField_02` | `u32` | 4 | `0x00881FF4` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

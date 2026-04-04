# CLIENT_CHAT_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0x7025` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Stall` | `u8` | 1 |  |
| 2 | `Length` | `u8` | 1 |  |
| 3 | `message` | `string` | var |  |


# SERVER_CHARACTER_SELECTION_JOIN_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0xB001` |
| Direction | Server → Client |
| Group | Server → Client |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `success` | `u8` | 1 |  |
| 2 | `errCode` | `u16` | 2 | if(success == 1) |


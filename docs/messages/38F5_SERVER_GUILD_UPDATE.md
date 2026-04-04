# SERVER_GUILD_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x38F5` |
| Direction | Server → Client |
| Group | Server → Client |

> Source: Server binary reverse engineering. See [server_binary_analysis.md](../server_binary_analysis.md).

### Fields (Server RE)

Most complex update packet in the server (31 code references).

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UpdateType` | `u8` | 1 | Guild update sub-type (member join/leave/promote, notice change, GP update, etc.) |

> **Note**: The full sub-type enumeration has not been fully reversed yet. The server has 31 code paths referencing this opcode, making it one of the most complex update packets. Partial sub-type documentation may be added as individual cases are confirmed.

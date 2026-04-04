# CLIENT_STALL_UPDATE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0x70BA` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `ItemUpdate` | `u8` | 1 |  |
| 2 | `slotStall` | `u8` | 1 |  |
| 3 | `quantity` | `u16` | 2 |  |
| 4 | `price` | `u64` | 8 |  |
| 5 | `unk` | `u16` | 2 |  |


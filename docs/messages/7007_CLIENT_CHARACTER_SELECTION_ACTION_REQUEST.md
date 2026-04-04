# CLIENT_CHARACTER_SELECTION_ACTION_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0x7007` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Create` | `u8` | 1 |  |
| 2 | `charname` | `string` | var |  |
| 3 | `model` | `u32` | 4 |  |
| 4 | `unk` | `u8` | 1 |  |
| 5 | `chest` | `u32` | 4 |  |
| 6 | `legs` | `u32` | 4 |  |
| 7 | `shoes` | `u32` | 4 |  |
| 8 | `weapon` | `u32` | 4 |  |


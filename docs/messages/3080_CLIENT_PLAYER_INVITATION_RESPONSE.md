# CLIENT_PLAYER_INVITATION_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x3080` |
| Direction | Dual (C↔S) |
| Group | Dual (C↔S) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `type` | `u8` | 1 |  |
| 2 | `uniqueID` | `u32` | 4 |  |
| 3 | `setup` | `u8` | 1 | case(SRTypes.PlayerPetition.ExchangeRequest) |


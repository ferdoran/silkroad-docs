# SERVER_PET_SETTINGS_CHANGE_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0xB420` |
| Direction | Server → Client |
| Group | Server → Client |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unk` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `uniqueID` | `u32` | 4 | if(packet.ReadBool() |
| 3 | `settingsType` | `u8` | 1 | if(packet.ReadBool() |
| 4 | `SettingsFlags` | `u32` | 4 | if(packet.ReadBool() → case(1) |


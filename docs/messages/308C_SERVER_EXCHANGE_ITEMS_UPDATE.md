# SERVER_EXCHANGE_ITEMS_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x308C` |
| Direction | Server → Client |
| Group | Server → Client |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unk` | `u32` | 4 |  |
| 2 | `unk` | `u8` | 1 | if(InfoManager.Character == player) |
| 3 | `slotInventory` | `u8` | 1 | if(InfoManager.Character == player) |
| 4 | `slotExchange` | `u8` | 1 | if(InfoManager.Character == player) → if(player == InfoManager.Character) |


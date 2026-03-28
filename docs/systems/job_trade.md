# Job & Trade System

The Job system (also called the Trade system) is one of Silkroad Online's defining features.
Players choose between three job types — Merchant, Thief, and Hunter — and participate in a
trade route economy where merchants transport specialty goods between towns while thieves
attempt to steal them and hunters protect the caravans.

## Job Types

| Type | Enum | Description |
|------|------|-------------|
| None | 0 | No job selected |
| Merchant | 1 | Transports trade goods between towns for profit |
| Thief | 2 | Attacks merchants to steal goods; earns gold from stolen items |
| Hunter | 3 | Protects merchants from thieves; earns bounty rewards |

## Related Opcodes

### Client → Server

| Opcode | Name | Description |
|--------|------|-------------|
| `0xB103` | CLIENT_JOB_REQUEST | Request job selection or job-related action |
| `0xB104` | CLIENT_JOB_ACTION | Perform job action (start trade, attack, protect) |
| `0xB105` | CLIENT_JOB_DATA | Request job data |
| `0xB106` | CLIENT_JOB_UPDATE | Update job state |
| `0xB107` | CLIENT_JOB_DETAIL | Request detailed job info |
| `0xB157` | CLIENT_JOB_ALIAS_DATA | Set job alias/nickname |

### Server → Client

| Opcode | Name | Description |
|--------|------|-------------|
| `0x3153` | SERVER_JOB_UPDATE | Job state update notification |
| `0x3154` | SERVER_JOB_DATA | Full job data response |
| `0x3156` | SERVER_JOB_ALIAS | Job alias confirmation |

## Related Classes

| Class | Purpose |
|-------|---------|
| `CIFJobAlias` | Job alias (nickname) UI interface |
| `CIFJobRank` | Job ranking display |
| `CIFSpecialtyDeal` | Specialty goods purchase/sale interface |
| `CIFTradeInfoWnd` | Trade route information window |

## Message Flow

### Selecting a Job

```
Client                          Server
  │                               │
  ├── CLIENT_JOB_REQUEST ────────→│  (type=SELECT, job_type=1/2/3)
  │                               │
  │←── SERVER_JOB_DATA ──────────┤  (job_type, rank, experience)
  │←── SERVER_JOB_UPDATE ────────┤  (confirmation)
```

### Starting a Trade Run (Merchant)

```
Client                          Server
  │                               │
  ├── CLIENT_NPC_INTERACT ───────→│  (interact with specialty goods NPC)
  │←── SERVER_NPC_RESPONSE ──────┤  (shop window with trade goods)
  │                               │
  ├── CLIENT_JOB_ACTION ─────────→│  (action=BUY_TRADE_GOODS, item_id, qty)
  │←── SERVER_INVENTORY_ITEM ────┤  (trade goods added to transport)
  │←── SERVER_JOB_UPDATE ────────┤  (trade state: IN_TRANSIT)
  │                               │
  │  ... player travels to destination ...
  │                               │
  ├── CLIENT_NPC_INTERACT ───────→│  (interact with destination NPC)
  ├── CLIENT_JOB_ACTION ─────────→│  (action=SELL_TRADE_GOODS)
  │←── SERVER_JOB_UPDATE ────────┤  (trade complete, gold earned, job XP)
```

## Data Tables

### Related Tables

- **itemdata**: Trade goods have codenames matching `ITEM_ETC_TRADE_*` and `ITEM_ETC_SPECIALTY_*`
- **npcpos**: Trade NPC positions (specialty goods vendors at each town)
- **teleportdata**: Town locations connected by trade routes
- **refpricepolicyofitem**: Price policies affecting trade good buy/sell prices

### Job Experience & Ranks

Job experience is tracked separately from character experience. As job experience increases, players unlock higher job ranks with better rewards. The ranking system is visible via the `CIFJobRank` interface.

## Trade Routes

Trade routes connect major towns across the game world. The further the distance, the higher the profit but also the higher the risk. Key routes:

- **Jangan ↔ Donwhang**: Short Chinese route, low profit/risk
- **Jangan ↔ Hotan**: Medium Chinese route
- **Constantinople ↔ Samarkand**: Long cross-continent route, high profit/risk

## Specialty Goods

Specialty goods are town-specific items purchased from NPCs. Their sale price increases with distance from the origin town. Goods are carried in a special transport inventory separate from the regular inventory.

## PvP Interactions

When a merchant is transporting goods:

- **Thieves** can attack the merchant. Killing the merchant drops the trade goods, which the thief can pick up and sell at a thief NPC.
- **Hunters** can attack thieves near merchants. Hunters earn bounty rewards for killing thieves.
- **Merchants** can hire NPC guards or team up with hunter players for protection.

Job PvP flags are tracked via opcodes `0xB0FD` / `0x3122` (PVP update).

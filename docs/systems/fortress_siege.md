# Fortress Siege System

The Fortress Siege system is Silkroad Online's large-scale guild PvP feature.
Guilds compete to capture and hold fortresses, which grant the owning guild
tax revenue from the surrounding region.

## State Machine

The fortress operates on a weekly cycle with distinct states:

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   DEFAULT    │────→│   REQUEST    │────→│     WAR      │────→│     TAX      │
│ (Normal ops) │     │(Registration)│     │ (Battle)     │     │(Revenue)     │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
       ↑                                                            │
       └────────────────────────────────────────────────────────────┘
```

| State | Duration | Description |
|-------|----------|-------------|
| DEFAULT | Most of the week | Normal fortress operations, tax collection |
| REQUEST | ~24 hours before war | Guilds register for siege, pay entry fee |
| WAR | ~2 hours | Active battle phase |
| TAX | After war | Tax redistribution period |

The state transitions are logged with debug strings like `"FORTRESS STATE"` in the client.

## Related Opcodes

### Client → Server

| Opcode | Name | Description |
|--------|------|-------------|
| `0xB05D` | CLIENT_SIEGE_REQUEST | Siege registration/request |
| `0xB05E` | CLIENT_SIEGE_RESPONSE | Response to siege prompts |
| `0xB060` | CLIENT_SIEGE_ACTION | Siege actions during battle |
| `0xB461` | CLIENT_FORTRESS_REQUEST | Fortress info request |
| `0xB462` | CLIENT_FORTRESS_ACTION | Fortress management actions |
| `0xB463` | CLIENT_FORTRESS_DATA | Request fortress data |
| `0xB4D4` | CLIENT_FORTRESS_UPDATE | Fortress update request |

### Server → Client

| Opcode | Name | Description |
|--------|------|-------------|
| `0x30EF` | SERVER_SIEGE_DATA | Siege state and participant data |
| `0x34BE` | SERVER_FORTRESS_DATA | Fortress configuration data |
| `0x34D2` | SERVER_FORTRESS_UPDATE | Fortress state change notification |
| `0x34D5` | SERVER_FORTRESS_INFO | Fortress ownership/tax info |
| `0x34E1` | SERVER_FORTRESS_STATE | Fortress state machine transition |
| `0x34F2` | SERVER_FORTRESS_ACTION | Fortress action result |

## Data Tables

| Table | Rows | Description |
|-------|------|-------------|
| `siegefortress` | 4 | Fortress definitions (4 fortresses in the game) |
| `siegefortressbattlerank` | 7 | Battle rank thresholds and rewards |
| `siegefortressguard` | 3,641 | NPC guard spawn configurations |
| `siegefortressitemforge` | 33 | Forge recipes for siege weapons |
| `siegefortressreward` | 5 | Victory/participation rewards |
| `siegestructupgradedata` | 63 | Structure upgrade paths |
| `refsiegeblessbuff` | 9 | Siege blessing buffs |
| `refsiegedungeon` | 4 | Siege dungeon configurations |

## Fortress Structures

During the REQUEST phase, the fortress owner can build defensive structures:

| Structure Type | Purpose |
|---------------|---------|
| Gate | Main entrance — must be destroyed by attackers |
| Tower | Ranged attack tower — fires at enemies in range |
| Guard Tower | Spawns NPC guards |
| Command Post | Central objective — capturing wins the siege |

Structures can be upgraded using the `siegestructupgradedata` table.

## Battle Ranks

During WAR phase, participants earn contribution points for kills and objective actions.
The `siegefortressbattlerank` table defines rank thresholds:

| Rank | Points Required | Reward |
|------|----------------|--------|
| 1 | Lowest threshold | Basic participation reward |
| 7 | Highest threshold | Maximum siege reward |

## Message Flow

### Siege Registration

```
Client (Guild Master)           Server
  │                               │
  ├── CLIENT_FORTRESS_REQUEST ───→│  (action=REGISTER)
  │                               │  (checks: guild level, gold fee)
  │←── SERVER_FORTRESS_DATA ─────┤  (registration confirmed)
  │                               │
  │←── SERVER_FORTRESS_STATE ────┤  (state: REQUEST)
```

### Battle Phase

```
All Participants                Server
  │                               │
  │←── SERVER_FORTRESS_STATE ────┤  (state: WAR — battle begins)
  │←── SERVER_SIEGE_DATA ────────┤  (participant list, structure HP)
  │                               │
  ├── CLIENT_SIEGE_ACTION ───────→│  (attack structure / player)
  │←── SERVER_FORTRESS_UPDATE ───┤  (structure HP update)
  │←── SERVER_FORTRESS_ACTION ───┤  (action result)
  │                               │
  │  ... battle continues ...     │
  │                               │
  │←── SERVER_FORTRESS_STATE ────┤  (state: TAX — battle ends)
  │←── SERVER_FORTRESS_INFO ─────┤  (new owner, tax info)
```

## Tax System

The fortress owner collects tax revenue from:
- NPC shop transactions in the fortress region
- Teleport fees through the region
- Trade goods passing through the region

Tax rates are configurable by the fortress owner within server-defined limits.
Revenue is distributed weekly at the state transition from TAX → DEFAULT.

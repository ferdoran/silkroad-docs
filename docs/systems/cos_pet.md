# COS (Pet & Transport) System

COS (Creature On Sight) is the system governing pets, mounts, and transport vehicles
in Silkroad Online. COS entities are summoned companions that follow the player and
provide combat assistance, transportation, or storage.

## COS Types

| Type | Description | Example |
|------|-------------|---------|
| Attack Pet | Fights alongside the player, earns XP | White Tiger, Eagle |
| Pick Pet | Automatically picks up dropped items | Rabbit, Cat |
| Mount (Horse) | Increases movement speed | Various horse types |
| Transport | Carries trade goods, has HP bar | Donkey, Camel, Horse Cart |
| Special COS | Event or premium companions | Devil Spirit, Angel Spirit |

## Related Opcodes

### Client → Server

| Opcode | Name | Description |
|--------|------|-------------|
| `0xB0C0` | CLIENT_PET_REQUEST | Pet/COS general request |
| `0xB0C5` | CLIENT_PET_ACTION | Pet action (summon, unsummon, rename) |
| `0xB110` | CLIENT_COS_REQUEST | COS spawn/control request |
| `0xB112` | CLIENT_COS_ACTION | COS action command |
| `0xB113` | CLIENT_COS_DATA | Request COS data |
| `0xB114` | CLIENT_COS_UPDATE | COS state update |
| `0xB116` | CLIENT_COS_INFO | Request COS info |
| `0xB15F` | CLIENT_COS_REMOVE | Dismiss/unsummon COS |

### Server → Client

| Opcode | Name | Description |
|--------|------|-------------|
| `0x30D0` | SERVER_PET_RESPONSE | Pet request response |
| `0x30D1` | SERVER_PET_DATA | Pet full data |
| `0x30D3` | SERVER_PET_STATUS | Pet status update (HP, hunger) |
| `0x30D4` | SERVER_PET_UPDATE | Pet state change |
| `0x30D5` | SERVER_PET_EXPERIENCE | Pet XP gain notification |
| `0x3159` | SERVER_COS_SPAWN | COS entity spawned in world |
| `0x315A` | SERVER_COS_UPDATE | COS state update |
| `0x315B` | SERVER_COS_DATA | COS full data |
| `0x315C` | SERVER_COS_REMOVE | COS removed from world |
| `0x315D` | SERVER_COS_SETTINGS | COS configuration |
| `0x315E` | SERVER_COS_INFO | COS information |
| `0x3161` | SERVER_COS_INFO_2 | Extended COS information |

## Related Classes

| Class | Purpose |
|-------|---------|
| `CCOSDataMgr` | Central COS data management |
| `CIFCOS` | COS UI interface |
| `CICCos` | COS item/inventory component |

## COS Data Structure

Each COS entity has:

```
COS Entity
├── unique_id: u32      — World-unique entity ID
├── owner_id: u32       — Owning player's entity ID
├── model_id: u32       — Character data reference (characterdata table)
├── name: string        — Custom name (given by player)
├── level: u8           — Pet level (1-50 for attack pets)
├── hp_current: u32     — Current HP
├── hp_max: u32         — Maximum HP
├── exp: u64            — Experience points
├── hunger: u8          — Hunger level (0-100, decreases over time)
├── state: u8           — Active/Inactive/Dead
└── settings: u32       — Bitmask for behavior settings
```

## Message Flow

### Summoning a Pet

```
Client                          Server
  │                               │
  ├── CLIENT_PET_REQUEST ────────→│  (action=SUMMON, inventory_slot)
  │                               │  (validates: pet scroll in inventory)
  │←── SERVER_PET_RESPONSE ──────┤  (success/fail)
  │←── SERVER_PET_DATA ──────────┤  (full pet data: level, HP, name)
  │←── SERVER_COS_SPAWN ────────┤  (spawn in world for all nearby)
  │←── SERVER_ENTITY_SPAWN ─────┤  (entity spawn for nearby players)
```

### Pet Combat (Attack Pet)

```
Client                          Server
  │                               │
  │  (player attacks monster)     │
  ├── CLIENT_ENTITY_ACTION ──────→│
  │                               │  (pet auto-targets same monster)
  │←── SERVER_ENTITY_ACTION ─────┤  (pet attack animation)
  │←── SERVER_ENTITY_DAMAGE ─────┤  (pet damage dealt)
  │                               │
  │  (monster dies)               │
  │←── SERVER_PET_EXPERIENCE ────┤  (pet XP gain)
  │←── SERVER_PET_STATUS ────────┤  (updated HP if damaged)
```

### Feeding a Pet

Pets have a hunger system. Hunger decreases over time and when HP is 0 the pet dies.
Feeding uses a pet food item from inventory:

```
Client                          Server
  │                               │
  ├── CLIENT_PET_ACTION ─────────→│  (action=FEED, food_item_slot)
  │←── SERVER_PET_STATUS ────────┤  (hunger restored)
  │←── SERVER_INVENTORY_OPERATION┤  (food item consumed)
```

## Transport COS

Transport COS (donkeys, camels, horse carts) are used in the Trade system:

- Spawned from transport scrolls
- Have a dedicated inventory for trade goods
- Visible to other players (can be attacked by thieves)
- Movement speed varies by type (donkey < camel < horse cart)
- HP bar visible — if destroyed, trade goods drop

### Transport Inventory

```
Client                          Server
  │                               │
  ├── CLIENT_COS_ACTION ─────────→│  (action=OPEN_INVENTORY)
  │←── SERVER_COS_DATA ─────────┤  (transport inventory contents)
  │                               │
  ├── CLIENT_INVENTORY_MOVE ─────→│  (move trade goods to transport)
  │←── SERVER_INVENTORY_OPERATION┤  (item moved confirmation)
```

## Pet Death & Revival

When a pet's HP reaches 0:
1. `SERVER_PET_STATUS` sent with HP=0
2. `SERVER_COS_REMOVE` removes from world
3. Pet scroll changes to "dead" state in inventory
4. Revival requires a revival scroll item or NPC service

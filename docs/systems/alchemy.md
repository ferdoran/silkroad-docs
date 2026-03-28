# Alchemy & Enchantment System

The Alchemy system encompasses all item enhancement mechanics in Silkroad Online:
reinforcement (plus levels), enchantment (magic options), manufacturing, and decomposition.

## Alchemy Operations

| Operation | Description |
|-----------|-------------|
| **Reinforce** | Increase item's plus level (+1 to +12), boosts base stats |
| **Enchant** | Add magic options (blue stats) to equipment |
| **Manufacture** | Craft alchemy stones and elixirs from materials |
| **Decompose** | Break down equipment into raw materials |

## Related Opcodes

### Client → Server

| Opcode | Name | Description |
|--------|------|-------------|
| `0xB0DB` | CLIENT_ALCHEMY_REQUEST | All alchemy operations |

### Server → Client

| Opcode | Name | Description |
|--------|------|-------------|
| `0x30DF` | SERVER_ALCHEMY_RESPONSE | Alchemy operation result |
| `0x30E0` | SERVER_ALCHEMY_DATA | Alchemy data/state |

## Related Classes

| Class | Purpose |
|-------|---------|
| `CAlchemyMgr` | Core alchemy logic — manages all operations |
| `CIFAlchemy` | Alchemy UI base interface |
| `CIFAlchemyReinforce` | Reinforcement UI |
| `CIFAlchemyEnchant` | Enchantment UI |
| `CIFAlchemyManufacture` | Manufacturing UI |

## Data Tables

| Table | Rows | Description |
|-------|------|-------------|
| `magicoption` | 391 | All magic option definitions (stat types and values) |
| `magicoptionassign` | 74 | Assignment rules — which options can go on which items |
| `refmagicoptgroup` | 88 | Option grouping for enchantment |
| `refmagicoptbyitemoptleveldata` | 251 | Option values scaled by item opt level |
| `refabilitybyitemoptleveldata` | 90 | Ability modifiers by item opt level |
| `refskillbyitemoptleveldata` | 154 | Skill bonuses by item opt level |

## Reinforcement (+1 to +12)

Reinforcement increases an item's base stats. Each plus level requires:
- The target equipment item
- An alchemy stone (weapon/armor/accessory specific)
- Optional: luck stone to improve success rate

### Success Rates

| Level | Base Rate | With Luck Stone |
|-------|-----------|----------------|
| +1 to +3 | High (~80%) | Near 100% |
| +4 to +6 | Medium (~50%) | ~70% |
| +7 to +9 | Low (~30%) | ~50% |
| +10 to +12 | Very low (~10%) | ~25% |

On failure:
- Item may lose 1 plus level (downgrade)
- Item may be destroyed (at higher levels)
- Luck stone is always consumed

### Message Flow

```
Client                          Server
  │                               │
  ├── CLIENT_ALCHEMY_REQUEST ────→│  (type=REINFORCE,
  │                               │   item_slot, stone_slot,
  │                               │   luck_slot [optional])
  │                               │
  │←── SERVER_ALCHEMY_RESPONSE ──┤  (result: SUCCESS/FAIL/DESTROY)
  │←── SERVER_ITEM_UPDATE ───────┤  (updated item stats if success)
  │←── SERVER_INVENTORY_OPERATION┤  (stone consumed)
```

## Enchantment (Magic Options)

Enchantment adds "blue stats" (magic options) to equipment using magic tablets.

### Magic Option Types (from `magicoption` table)

| Codename Pattern | Effect |
|-----------------|--------|
| `MATTR_DEC_*` | Decrease attribute (negative) |
| `MATTR_INC_*` | Increase attribute (positive) |
| `MATTR_STR` | Strength bonus |
| `MATTR_INT` | Intelligence bonus |
| `MATTR_HP` | HP bonus |
| `MATTR_MP` | MP bonus |
| `MATTR_LUCK` | Luck bonus |
| `MATTR_SPEED` | Movement speed bonus |
| `MATTR_CRITICAL` | Critical rate bonus |
| `MATTR_BLOCK` | Block rate bonus |

### Magic Option Assignment

The `magicoptionassign` table defines which options can appear on which item types.
Each assignment rule specifies:
- Item type range (weapon, armor, accessory)
- Available option pool
- Option degree (rarity/power level)
- Value range

## Manufacturing

Manufacturing creates alchemy stones, elixirs, and other materials from base components.

```
Client                          Server
  │                               │
  ├── CLIENT_ALCHEMY_REQUEST ────→│  (type=MANUFACTURE,
  │                               │   recipe_id, material_slots[])
  │                               │
  │←── SERVER_ALCHEMY_RESPONSE ──┤  (result: SUCCESS + created item)
  │←── SERVER_INVENTORY_ITEM ────┤  (new item in inventory)
```

## Decomposition

Decomposition breaks equipment into raw alchemy materials. Higher plus levels and rarer items yield better materials.

```
Client                          Server
  │                               │
  ├── CLIENT_ALCHEMY_REQUEST ────→│  (type=DECOMPOSE, item_slot)
  │                               │
  │←── SERVER_ALCHEMY_RESPONSE ──┤  (result: materials obtained)
  │←── SERVER_INVENTORY_OPERATION┤  (original item removed)
  │←── SERVER_INVENTORY_ITEM ────┤  (materials added)
```

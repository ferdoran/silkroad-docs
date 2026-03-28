# Guild System

The Guild system allows players to form organizations with hierarchical ranks, shared storage,
guild wars, alliances (unions), and fortress ownership.

## Related Opcodes

### Client → Server

| Opcode | Name | Description |
|--------|------|-------------|
| `0xB0BA` | CLIENT_GUILD_REQUEST | General guild operations |
| `0xB308` | CLIENT_GUILD_REQUEST_2 | Extended guild operations |
| `0xB309` | CLIENT_GUILD_UPDATE | Update guild info |
| `0xB30A` | CLIENT_GUILD_ACTION | Guild actions (invite, kick, promote) |
| `0xB30B` | CLIENT_GUILD_DATA | Request guild data |
| `0xB30C` | CLIENT_GUILD_INFO | Request guild info |
| `0xB30D` | CLIENT_GUILD_DETAIL | Request detailed guild info |

### Server → Client

| Opcode | Name | Description |
|--------|------|-------------|
| `0x30A6` | SERVER_GUILD_INFO | Guild information response |
| `0x3120` | SERVER_ENTITY_UPDATE_GUILD | Entity guild affiliation update |
| `0x747E` | SERVER_GUILD_DATA | Full guild data response |

## Related Classes

| Class | Purpose |
|-------|---------|
| `CGuildManager` | Core guild logic and state management |
| `CNIFGuildWnd` | Main guild window UI |
| `CIFGuildMember` | Guild member list interface |
| `CIFGuildStorage` | Guild shared storage interface |
| `CIFGuildWar` | Guild war declaration interface |

## Guild Hierarchy

| Rank | Name | Permissions |
|------|------|-------------|
| 0 | Guild Master | Full control: disband, promote/demote all, war declaration |
| 1 | Vice Master | Invite, kick lower ranks, manage storage |
| 2 | Captain | Invite members |
| 3 | Senior Member | Access guild chat |
| 4 | Member | Basic member |

## Message Flow

### Guild Creation

```
Client                          Server
  │                               │
  ├── CLIENT_GUILD_REQUEST ──────→│  (action=CREATE, guild_name)
  │                               │  (requires: level 20+, gold fee)
  │←── SERVER_GUILD_INFO ────────┤  (guild_id, name, master_name)
  │←── SERVER_ENTITY_UPDATE_GUILD┤  (player's guild tag now visible)
```

### Inviting a Member

```
Client (Master)                 Server                     Client (Target)
  │                               │                               │
  ├── CLIENT_GUILD_ACTION ───────→│  (action=INVITE, target_name) │
  │                               ├── SERVER_GUILD_INFO ─────────→│ (invite prompt)
  │                               │                               │
  │                               │←── CLIENT_GUILD_REQUEST ─────┤ (action=ACCEPT)
  │←── SERVER_GUILD_DATA ────────┤                               │
  │                               ├── SERVER_GUILD_DATA ─────────→│ (full guild data)
  │                               ├── SERVER_ENTITY_UPDATE_GUILD →│ (guild tag)
```

### Guild War Declaration

```
Client (Master A)               Server                     All Guild B Members
  │                               │                               │
  ├── CLIENT_GUILD_ACTION ───────→│  (action=DECLARE_WAR,         │
  │                               │   target_guild_id, gold_bet)  │
  │                               │                               │
  │←── SERVER_GUILD_INFO ────────┤  (war state: PENDING)         │
  │                               ├── SERVER_GUILD_INFO ─────────→│ (war declaration)
  │                               │                               │
  │  ... Guild B master accepts ...                               │
  │                               │                               │
  │←── SERVER_GUILD_INFO ────────┤  (war state: ACTIVE)          │
  │                               ├── SERVER_GUILD_INFO ─────────→│ (war active)
```

## Guild Unions (Alliances)

Guilds can form alliances called "Unions". A union is led by one guild master and can contain multiple guilds. Union members share:

- Union chat channel
- Cannot attack each other
- Shared fortress siege participation

Related opcode: `0x751A` SERVER_UNION_DATA.

## Guild Storage

Guild storage is a shared inventory accessible by members with appropriate rank permissions. Managed through `CIFGuildStorage` and accessed via `CLIENT_STORAGE_REQUEST` / `CLIENT_STORAGE_ACTION` opcodes.

## Guild Points & Level

Guilds earn GP (Guild Points) through member activities:
- Monster kills
- Trade route completions
- Fortress siege participation
- PvP kills during guild wars

GP determines guild level, which unlocks:
- Increased member capacity
- Guild storage expansion
- Guild emblem customization
- Fortress siege eligibility

# vSRO Server Binary Reverse Engineering

Analysis of `SR_GameServer_Andreas.exe` (8.5MB, PE32 x86) and `AgentServer.exe` (912KB, PE32 x86).
Cross-referenced with existing client-side documentation.

## Key Findings Summary

- **Dispatch Table**: Base `0xCCF110`, 2048 entries × 8 bytes, indexed by `opcode & 0x7FF`
- **Unhandled Handler**: `0x4B0DD0` — logs `"Unhandled Game SR_MSG: 0x%x [data size: %d]"`
- **10 hot-path handlers** registered in static init; remaining handlers registered dynamically via `CCmdDispatcher`
- **160+ IGObj interface methods** recovered from assert strings
- **60+ stored procedures** recovered (revealing DB schema)
- **Rich RTTI**: Full class hierarchy — `CGObj` → `CGObjMobile` → `CGObjChar` → `CGObjPC`/`CGObjMob`/`CGObjNPC`/`CGObjCOS_*`
- **Server state enums** recovered: LifeState, MotionState, BodyMode, BattleState, PvPState

---

## 1. Server Architecture

### Class Hierarchy (from RTTI)

```
IGObj (interface)
└── CGObj
    ├── CGObjStruct
    │   ├── CGObjSiegeStruct
    │   └── CGObjSiegeObject
    ├── CGObjMobile
    │   └── CGObjMover / CGObjMoverByCmd / CGObjMoverByDest
    └── CGObjChar
        ├── CGObjPC (Player Character)
        │   ├── CGObjPC_COSManager
        │   ├── CGObjPC_QuestManager
        │   └── CGObjPC_SpotManager
        ├── CGObjMob (Monster)
        ├── CGObjNPC
        │   └── CGObjNPCNPC
        ├── CGObjEventZone
        └── CGObjCOS (Companion/Service)
            ├── CGObjCOS_Cart
            ├── CGObjCOS_Pet
            │   ├── CGObjCOS_GoldPet
            │   └── CGObjCOS_SilkPet
            ├── CGObjCOS_Summoned
            ├── CGObjCOS_Mercenary
            ├── CGObjCOS_Captured
            ├── CGObjCOS_Follower
            └── CGObjCOS_Assaulter
```

### Server Framework Classes

```
ServerFramework::CServerProcessMain
ServerFramework::CServerProcessOverlap
ServerFramework::CServerApp
CSession
CCmdDispatcher (singleton - opcode dispatch)
CGObjFactory (singleton - object creation)
CGame (main game loop)
CGameAI
CEventHandler / CEventHandlerList / CGObjEventHandler
CMaintainer
```

### Event System Classes (Fortress of Roc, Battle Arena, Flag World)

```
ROCTOP_WORLD_EVENT_HANDLERS::OnUpdate, OnRocDead, OnSealStoneDead, OnSoulDead, OnTimer*
ROCFRONT_WORLD_EVENT_HANDLERS::OnUpdate, OnDead, OnLeaveWorld, OnPartyStatusChanged
BATTLE_ARENA_EVENT_HANDLERS::OnUpdate_Arena, OnDead, OnDead_Monster, OnSelectObj, OnResurrectMyChar
FLAG_WORLD_EVENT_HANDLERS::OnUpdate_FlagChecker, OnDead_Monster_Key, OnDropItems, etc.
```

---

## 2. Server State Enums (from binary strings)

### LifeState
```
LIFESTATE_EMBRYO    = 0  (spawning)
LIFESTATE_ALIVE     = 1
LIFESTATE_DEAD      = 2
LIFESTATE_GONE      = 3  (despawning)
```

### MotionState
```
MOTIONSTATE_STAND             = 0
MOTIONSTATE_WALK              = 1
MOTIONSTATE_RUN               = 2
MOTIONSTATE_SIT               = 3
MOTIONSTATE_SKILL             = 4
MOTIONSTATE_SKILL_ACTIONOFF   = 5
MOTIONSTATE_SKILL_KNOCKBACK   = 6
MOTIONSTATE_SKILL_PROTECTIONWALL = 7
MOTIONSTATE_HIT               = 8
MOTIONSTATE_KNOCKDOWN          = 9
MOTIONSTATE_STUN              = 10
MOTIONSTATE_FROZEN            = 11
MOTIONSTATE_COUNTERATTACK     = 12
MOTIONSTATE_PAO               = 13
MOTIONSTATE_RIDE              = 14
MOTIONSTATE_SWIM              = 15
MOTIONSTATE_JUMP              = 16
MOTIONSTATE_REQ_HELP          = 17
MOTIONSTATE_CHANGEMOTION      = 18
```

### BodyMode
```
BODYMODE_NORMAL     = 0
BODYMODE_HWAN       = 1
BODYMODE_BERSERKER  = 2
BODYMODE_INVINCIBLE = 3
BODYMODE_INVISIBLE  = 4
```

### BattleState
```
BATTLESTATE_IN_PEACE  = 0
BATTLESTATE_IN_BATTLE = 1
```

### PvPState
```
PvPSTATE_NEUTRAL    = 0
PvPSTATE_ASSAULTER  = 1
PvPSTATE_MURDERER   = 2
```

### Message Processing State
```
MSG_PROCSTATE_NORMAL      = 0
MSG_PROCSTATE_BLOCKED     = 1
MSG_PROCSTATE_OVERLAPPED  = 2
```

---

## 3. Opcode Dispatch Table

### Table Structure
- **Base Address**: `0xCCF110` (runtime BSS)
- **Size**: 2048 entries (0x000..0x7FF)
- **Entry Format**: 8 bytes = `[handler_func_ptr:u32][this_offset:u32]`
- **Index Calculation**: `opcode & 0x7FF`
- **Validation**: `(opcode & 0xFFF) == (opcode & 0x7FF)` — if not equal, packet is rejected as unhandled

### Static Handler Registrations (from init at `0x4B0B70`)

| Index | Opcode(s) | Handler | Name |
|-------|-----------|---------|-------------------|
| 0x021 | 0x7021 | 0x4B23E0 | CLIENT_CHARACTER_MOVEMENT |
| 0x022 | 0x7022 | 0x4B2410 | (unknown — likely movement sub-type) |
| 0x023 | 0x7023 | 0x4B2430 | (unknown — likely movement sub-type) |
| 0x024 | 0x7024 | 0x4B23C0 | CLIENT_CHARACTER_MOVEMENT_ANGLE |
| 0x025 | 0x7025 | 0x4B2420 | CLIENT_CHAT_REQUEST |
| 0x034 | 0x7034 | 0x51CB30 | CLIENT_INVENTORY_ITEM_MOVEMENT |
| 0x04F | 0x704F | 0x4B23F0 | (unknown — possibly CLIENT_CHARACTER_HGP_USE) |
| 0x068 | 0x7068 | 0x4B2440 | (unknown) |
| 0x074 | 0x7074 | 0x4B2400 | CLIENT_CHARACTER_ACTION_REQUEST |
| 0x091 | 0x3091 | 0x4B23D0 | CLIENT_CHARACTER_EMOTE_USE |

---

## 4. Corrected Opcode Map (Server Cross-Reference)

### Client → Server (0x7xxx, 0x3xxx, 0x6xxx)

| Opcode | Name | Table Index |
|--------|-----------|-------------|
| 0x6103 | CLIENT_AUTH_REQUEST | 0x103 |
| 0x7001 | CLIENT_CHARACTER_SELECTION_JOIN_REQUEST | 0x001 |
| 0x7007 | CLIENT_CHARACTER_SELECTION_ACTION_REQUEST | 0x007 |
| 0x7010 | CLIENT_GAMEMASTER_COMMAND_REQUEST | 0x010 |
| 0x3012 | CLIENT_CHARACTER_CONFIRM_SPAWN | 0x012 |
| 0x7021 | CLIENT_CHARACTER_MOVEMENT | 0x021 |
| 0x7024 | CLIENT_CHARACTER_MOVEMENT_ANGLE | 0x024 |
| 0x7025 | CLIENT_CHAT_REQUEST | 0x025 |
| 0x7034 | CLIENT_INVENTORY_ITEM_MOVEMENT | 0x034 |
| 0x703C | CLIENT_STORAGE_DATA_REQUEST | 0x03C |
| 0x7045 | CLIENT_ENTITY_SELECTION | 0x045 |
| 0x7046 | CLIENT_ENTITY_TALK_REQUEST | 0x046 |
| 0x704B | CLIENT_NPC_CLOSE_REQUEST | 0x04B |
| 0x704C | CLIENT_INVENTORY_ITEM_USE | 0x04C |
| 0x7050 | CLIENT_CHARACTER_ADD_STR_REQUEST | 0x050 |
| 0x7051 | CLIENT_CHARACTER_ADD_INT_REQUEST | 0x051 |
| 0x3053 | CLIENT_CHARACTER_AUTORESURRECTION | 0x053 |
| 0x7059 | CLIENT_TELEPORT_RECALL_REQUEST | 0x059 |
| 0x705A | CLIENT_TELEPORT_USE_REQUEST | 0x05A |
| 0x7060 | CLIENT_PARTY_CREATION_REQUEST | 0x060 |
| 0x7061 | CLIENT_PARTY_LEAVE | 0x061 |
| 0x7062 | CLIENT_PARTY_INVITATION_REQUEST | 0x062 |
| 0x7063 | CLIENT_PARTY_KICK_REQUEST | 0x063 |
| 0x7069 | CLIENT_PARTY_MATCH_CREATION_REQUEST | 0x069 |
| 0x706A | CLIENT_PARTY_MATCH_EDITED_REQUEST | 0x06A |
| 0x706B | CLIENT_PARTY_MATCH_DELETE_REQUEST | 0x06B |
| 0x706C | CLIENT_PARTY_MATCH_LIST_REQUEST | 0x06C |
| 0x706D | CLIENT_PARTY_MATCH_JOIN_REQUEST | 0x06D |
| 0x306E | CLIENT_PARTY_MATCH_JOIN_RESPONSE | 0x06E |
| 0x7074 | CLIENT_CHARACTER_ACTION_REQUEST | 0x074 |
| 0x3080 | CLIENT_PLAYER_INVITATION_RESPONSE | 0x080 |
| 0x7081 | CLIENT_EXCHANGE_INVITATION_REQUEST | 0x081 |
| 0x7082 | CLIENT_EXCHANGE_CONFIRM_REQUEST | 0x082 |
| 0x7083 | CLIENT_EXCHANGE_APPROVE_REQUEST | 0x083 |
| 0x7084 | CLIENT_EXCHANGE_EXIT_REQUEST | 0x084 |
| 0x3091 | CLIENT_CHARACTER_EMOTE_USE | 0x091 |
| 0x70A1 | CLIENT_MASTERY_SKILL_LEVELUP_REQUEST | 0x0A1 |
| 0x70A2 | CLIENT_MASTERY_LEVELUP_REQUEST | 0x0A2 |
| 0x70B1 | CLIENT_STALL_CREATE_REQUEST | 0x0B1 |
| 0x70B2 | CLIENT_STALL_DESTROY_REQUEST | 0x0B2 |
| 0x70B3 | CLIENT_STALL_TALK_REQUEST | 0x0B3 |
| 0x70B4 | CLIENT_STALL_BUY_REQUEST | 0x0B4 |
| 0x70B5 | CLIENT_STALL_LEAVE_REQUEST | 0x0B5 |
| 0x70BA | CLIENT_STALL_UPDATE_REQUEST | 0x0BA |
| 0x70C5 | CLIENT_CHARACTER_PET_ACTION | 0x0C5 |
| 0x70CB | CLIENT_PET_MOUNTED | 0x0CB |
| 0x70F3 | CLIENT_GUILD_INVITATION_REQUEST | 0x0F3 |
| 0x70F9 | CLIENT_GUILD_NOTICE_EDIT_REQUEST | 0x0F9 |
| 0x7116 | CLIENT_PET_UNSUMMON_REQUEST | 0x116 |
| 0x7202 | CLIENT_MASTERY_SKILL_LEVELDOWN_REQUEST | 0x202 |
| 0x7203 | CLIENT_MASTERY_LEVELDOWN_REQUEST | 0x203 |
| 0x7250 | CLIENT_GUILD_STORAGE_REQUEST | 0x250 |
| 0x7309 | CLIENT_MAIL_SEND_REQUEST | 0x309 |
| 0x7420 | CLIENT_PET_SETTINGS_CHANGE_REQUEST | 0x420 |
| 0x7472 | CLIENT_ACADEMY_INVITATION_REQUEST | 0x472 |
| 0x7477 | CLIENT_ACADEMY_NOTICE_EDIT_REQUEST | 0x477 |
| 0x747D | CLIENT_ACADEMY_MATCH_LIST_REQUEST | 0x47D |
| 0x7508 | CLIENT_CONSIGNMENT_REGISTER_REQUEST | 0x508 |
| 0x7509 | CLIENT_CONSIGNMENT_UNREGISTER_REQUEST | 0x509 |
| 0x750E | CLIENT_CONSIGNMENT_LIST_REQUEST | 0x50E |
| 0x34B6 | CLIENT_TELEPORT_READY_RESPONSE | 0x4B6 |

### Server → Client (0x3xxx, 0xBxxx, 0xAxxx)

| Opcode | Name | Code Refs |
|--------|-----------|-----------|
| 0xA103 | SERVER_AUTH_RESPONSE | — |
| 0xB001 | SERVER_CHARACTER_SELECTION_JOIN_RESPONSE | 1 |
| 0xB007 | SERVER_CHARACTER_SELECTION_ACTION_RESPONSE | — |
| 0x34A5 | SERVER_CHARACTER_DATA_BEGIN | 1 |
| 0x3013 | SERVER_CHARACTER_DATA | 1 |
| 0x34A6 | SERVER_CHARACTER_DATA_END | 1 |
| 0x303D | SERVER_CHARACTER_STATS_UPDATE | 1 |
| 0x3056 | SERVER_CHARACTER_EXPERIENCE_UPDATE | 1 |
| 0x304E | SERVER_CHARACTER_INFO_UPDATE | 1 |
| 0x3011 | SERVER_CHARACTER_DIED | — |
| 0x3015 | SERVER_ENTITY_SPAWN | 1 |
| 0x3016 | SERVER_ENTITY_DESPAWN | 1 |
| 0x3017 | SERVER_ENTITY_GROUPSPAWN_BEGIN | 1 |
| 0x3018 | SERVER_ENTITY_GROUPSPAWN_END | 1 |
| 0x3019 | SERVER_ENTITY_GROUPSPAWN_DATA | 1 |
| 0xB021 | SERVER_ENTITY_MOVEMENT | 1 |
| 0xB023 | SERVER_ENTITY_MOVEMENT_STUCK | 1 |
| 0xB024 | SERVER_ENTITY_MOVEMENT_ANGLE | 1 |
| 0xB045 | SERVER_ENTITY_SELECTION | 2 |
| 0xB046 | SERVER_ENTITY_TALK_RESPONSE | 1 |
| 0x3054 | SERVER_ENTITY_LEVEL_UP | 2 |
| 0x3057 | SERVER_ENTITY_STATUS_UPDATE | 3 |
| 0x305C | SERVER_ENTITY_DISPLAY_EFFECT | 2 |
| 0x30D0 | SERVER_ENTITY_SPEED_UPDATE | 1 |
| 0x30BF | SERVER_ENTITY_STATE_UPDATE | 1 |
| 0xB070 | SERVER_ENTITY_SKILL_START | 3 |
| 0xB071 | SERVER_ENTITY_SKILL_END | 3 |
| 0xB0BD | SERVER_ENTITY_SKILL_BUFF_ADDED | 1 |
| 0xB072 | SERVER_ENTITY_SKILL_BUFF_REMOVED | 6 |
| 0x30B8 | SERVER_ENTITY_STALL_CREATE | 1 |
| 0x30B9 | SERVER_ENTITY_STALL_DESTROY | 1 |
| 0x30BB | SERVER_ENTITY_STALL_TITLE_UPDATE | 1 |
| 0x3091 | SERVER_ENTITY_EMOTE_USE | 2 |
| 0xB04C | SERVER_INVENTORY_ITEM_USE | 3 |
| 0xB034 | SERVER_INVENTORY_ITEM_MOVEMENT | 2 |
| 0x3052 | SERVER_INVENTORY_ITEM_DURABILITY_UPDATE | 1 |
| 0x3040 | SERVER_INVENTORY_ITEM_UPDATE | 2 |
| 0x3092 | SERVER_INVENTORY_CAPACITY_UPDATE | 1 |
| 0x3047 | SERVER_STORAGE_DATA_BEGIN | 1 |
| 0x3049 | SERVER_STORAGE_DATA | 2 |
| 0x3048 | SERVER_STORAGE_DATA_END | 1 |
| 0xB025 | SERVER_CHAT_RESPONSE | 3 |
| 0x3026 | SERVER_CHAT_UPDATE | 10 |
| 0x300C | SERVER_NOTICE_UPDATE | 11 |
| 0x3020 | SERVER_ENVIROMENT_CELESTIAL_POSITION | 1 |
| 0x3027 | SERVER_ENVIROMENT_CELESTIAL_UPDATE | 2 |
| 0x3809 | SERVER_ENVIROMENT_WEATHER_UPDATE | 2 |
| 0xB050 | SERVER_CHARACTER_ADD_STR_RESPONSE | 1 |
| 0xB051 | SERVER_CHARACTER_ADD_INT_RESPONSE | 1 |
| 0xB060 | SERVER_PARTY_INVITATION_RESPONSE | 3 |
| 0x3065 | SERVER_PARTY_DATA | 1 |
| 0x3864 | SERVER_PARTY_UPDATE | 6 |
| 0xB069 | SERVER_PARTY_MATCH_CREATION_RESPONSE | 1 |
| 0xB06A | SERVER_PARTY_MATCH_EDITED_RESPONSE | 1 |
| 0xB06B | SERVER_PARTY_MATCH_DELETE_RESPONSE | 1 |
| 0xB06C | SERVER_PARTY_MATCH_LIST_RESPONSE | 1 |
| 0x706D | SERVER_PARTY_MATCH_JOIN_REQUEST | 1 |
| 0x3080 | SERVER_PLAYER_PETITION_REQUEST | 2 |
| 0x30C8 | SERVER_PET_DATA | 1 |
| 0x30C9 | SERVER_PET_UPDATE | 10 |
| 0xB420 | SERVER_PET_SETTINGS_CHANGE_RESPONSE | 1 |
| 0xB0CB | SERVER_PET_PLAYER_MOUNTED | 2 |
| 0xB0B1 | SERVER_STALL_CREATE_RESPONSE | 1 |
| 0xB0B2 | SERVER_STALL_DESTROY_RESPONSE | 1 |
| 0xB0B3 | SERVER_STALL_TALK_RESPONSE | 1 |
| 0xB0B4 | SERVER_STALL_BUY_RESPONSE | 1 |
| 0xB0B5 | SERVER_STALL_LEAVE_RESPONSE | 1 |
| 0xB0BA | SERVER_STALL_UPDATE_RESPONSE | 1 |
| 0x30B7 | SERVER_STALL_ENTITY_ACTION | 4 |
| 0xB0A1 | SERVER_MASTERY_SKILL_LEVELUP_RESPONSE | 2 |
| 0xB0A2 | SERVER_MASTERY_LEVELUP_RESPONSE | 2 |
| 0xB202 | SERVER_MASTERY_SKILL_LEVELDOWN_RESPONSE | 2 |
| 0xB203 | SERVER_MASTERY_LEVELDOWN_RESPONSE | 2 |
| 0xB059 | SERVER_TELEPORT_RECALL_RESPONSE | 1 |
| 0xB05A | SERVER_TELEPORT_USE_RESPONSE | 2 |
| 0x34B5 | SERVER_TELEPORT_READY_REQUEST | 1 |
| 0x3085 | SERVER_EXCHANGE_STARTED | 1 |
| 0x3086 | SERVER_EXCHANGE_PLAYER_CONFIRMED | 1 |
| 0x3087 | SERVER_EXCHANGE_COMPLETED | 1 |
| 0x3088 | SERVER_EXCHANGE_CANCELED | 1 |
| 0x3089 | SERVER_EXCHANGE_GOLD_UPDATE | 1 |
| 0x308C | SERVER_EXCHANGE_ITEMS_UPDATE | 1 |
| 0xB081 | SERVER_EXCHANGE_INVITATION_RESPONSE | 1 |
| 0xB082 | SERVER_EXCHANGE_CONFIRM_RESPONSE | 1 |
| 0xB083 | SERVER_EXCHANGE_APPROVE_RESPONSE | 1 |
| 0xB084 | SERVER_EXCHANGE_EXIT_RESPONSE | 1 |
| 0x304D | SERVER_DROP_UNLOCKED | 1 |
| 0xB04B | SERVER_NPC_CLOSE_RESPONSE | 2 |
| 0x34B3 | SERVER_GUILD_DATA_BEGIN | 2 |
| 0x3101 | SERVER_GUILD_DATA | 2 |
| 0x34B4 | SERVER_GUILD_DATA_END | 2 |
| 0x38F5 | SERVER_GUILD_UPDATE | 31 |
| 0x30FF | SERVER_GUILD_PLAYER_LOG | 1 |
| 0xB0F0 | SERVER_GUILD_CREATED_DATA | — |
| 0xB250 | SERVER_GUILD_STORAGE_RESPONSE | 2 |
| 0x3253 | SERVER_GUILD_STORAGE_DATA_BEGIN | 1 |
| 0x3255 | SERVER_GUILD_STORAGE_DATA | 1 |
| 0x3254 | SERVER_GUILD_STORAGE_DATA_END | 1 |
| 0x3C81 | SERVER_ACADEMY_DATA | 1 |
| 0xB47D | SERVER_ACADEMY_MATCH_LIST_RESPONSE | 1 |
| 0xB508 | SERVER_CONSIGNMENT_REGISTER_RESPONSE | 3 |
| 0xB509 | SERVER_CONSIGNMENT_UNREGISTER_RESPONSE | 3 |
| 0xB309 | SERVER_MAIL_SEND_RESPONSE | 1 |

### Global (Handshake/System)

| Opcode | Name |
|--------|------|
| 0x5000 | GLOBAL_HANDSHAKE |
| 0x9000 | GLOBAL_HANDSHAKE_OK |
| 0x2001 | GLOBAL_IDENTIFICATION |
| 0x2002 | GLOBAL_PING |
| 0x2113 | GLOBAL_XTRAP_IDENTIFICATION |

---

## 5. Packet Structures (Server → Client)

### 0x3013 — SERVER_CHARACTER_DATA (via 0x34A5 begin / 0x34A6 end)

The full character data is sent as a multi-part message. Combined structure:

```
u32     ServerTimestamp
u32     RefObjID           // Character model ID
u8      Scale
u8      Level
u8      LevelMax
u64     Exp
u32     SPExp
u64     Gold
u32     SP                 // Skill Points
u16     StatPoints
u8      BerserkPoints
u32     GatheredExpPoint
u32     HPMax
u32     MPMax
u8      ExpIconType        // SRPlayer.ExpIcon enum
u8      PKDaily
u16     PKTotal
u32     PKPenalty
u8      BerserkLevel
u8      PVPCapeType        // SRPlayer.PVPCape enum

// Inventory
u8      InventoryCapacity
u8      ItemCount
for each item:
    u8      Slot
    ItemData (see Item Structure below)

// Avatar Inventory
u8      AvatarCapacity
u8      AvatarItemCount
for each item:
    u8      Slot
    ItemData

// Masteries
u8      unkByte01          // server: mastery section flag
while ReadBool() == true:
    u32     MasteryID
    u8      MasteryLevel

// Skills
u8      unkByte02          // server: skill section flag
while ReadBool() == true:
    u32     SkillID
    bool    Enabled

// Completed Quests
u16     CompletedQuestCount
for each:
    u32     QuestID

// Active Quests
u8      ActiveQuestCount
for each:
    u32     QuestID
    u8      Achievements
    bool    AutoShareRequired
    u8      QuestType
    if QuestType == 28:
        u32     TimeRemain
    u8      State
    if QuestType != 8:
        u8      ObjectiveCount
        for each objective:
            u8      ObjectiveID
            bool    Enabled
            ascii   Name
            u8      TaskCount
            u32[]   TasksID
    if QuestType == 88:
        u8      NpcCount
        u32[]   NpcsID

// Collection Books
u8      unkByte03          // server: collection book section flag
u32     BookCount
for each:
    u32     BookID
    u32     StartedDatetime    // SRTimeStamp
    u32     Pages              // bitmask of collected pages

// Position
u32     UniqueID
u16     RegionID
f32     PosX
f32     PosY
f32     PosZ
u16     Angle
bool    HasMovement
u8      MovementSpeedType  // 0=Walking, 1=Running
if HasMovement:
    if inDungeon(RegionID):
        u16  DestRegion, i32 DestX, i32 DestY, i32 DestZ
    else:
        u16  DestRegion, u16 DestX, u16 DestY, u16 DestZ
else:
    u8      MovementActionType
    u16     Angle

// States
u8      LifeState          // LIFESTATE_* enum
u8      unkByte04          // server: BodyMode (BODYMODE_* enum)
u8      MotionState        // MOTIONSTATE_* enum
u8      GameState          // server: BattleState (BATTLESTATE_* enum)
f32     SpeedWalking
f32     SpeedRunning
f32     SpeedBerserk

// Buffs
u8      BuffCount
for each buff:
    u32     SkillID
    u32     BuffUniqueID
    if hasAutoTransferEffect:
        bool    IsCaster
        if IsCaster:
            (CasterUniqueID = entity UniqueID)

// Identification
ascii   Name
ascii   JobName            // Trade job codename
u8      JobType            // 0=None, 1=Trader, 2=Thief, 3=Hunter
u8      JobLevel
u32     JobExp
u32     JobContribution
u32     JobReward
u8      PVPState           // PvPSTATE_* enum
bool    IsRiding
bool    InCombat           // BATTLESTATE
if IsRiding:
    u32     RidingUniqueID
u8      CaptureTheFlagType
u64     GuideFlag          // Tutorial completion bitmask
u32     JoinID             // JID (player session ID)
bool    IsGameMaster

// Game Settings (config data follows, structure varies)
```

### 0x3015 — SERVER_ENTITY_SPAWN

```
u32     RefObjID

// Branch based on RefObjID type:

IF isSkillZone(RefObjID):
    u16     unkUShort01
    u32     SkillID
    u32     UniqueID
    u16     RegionID
    f32     PosX, PosY, PosZ
    u16     Angle

ELIF isModel(RefObjID):
    IF isPlayer:
        u8      Scale
        u8      BerserkLevel
        u8      PVPCapeType
        u8      ExpIconType
        // Equipment Inventory
        u8      EquipMaxCapacity    // appears unused
        u8      EquipCount
        for each:
            u32     RefItemID
            if isEquipable: u8 Plus
        // Avatar Inventory
        u8      AvatarMaxCapacity
        u8      AvatarCount
        for each:
            u32     RefItemID
            if isEquipable: u8 Plus
        // Mask (Transform)
        bool    HasMask
        if HasMask:
            u32     MaskRefObjID
            if same model type as player:
                u8      MaskScale
                u8      MaskEquipCount
                u32[]   MaskEquipIDs

    ELIF isNPC && isFortressStruct:
        u32     HP
        u32     RefEventStructID
        u16     State

    // Position (all models)
    u32     UniqueID
    u16     RegionID
    f32     PosX, PosY, PosZ
    u16     Angle
    // Movement
    bool    HasMovement
    u8      MovementSpeedType
    if HasMovement:
        if inDungeon: u16 DestRegion, i32 DestX/Y/Z
        else: u16 DestRegion, u16 DestX/Y/Z
    else:
        u8      MovementActionType
        u16     Angle
    // States
    u8      LifeState          // server: GetLifeState()
    u8      unkByte01          // server: BodyMode / GetBodyMode()
    u8      MotionState        // server: GetMotionState()
    u8      GameState          // server: BattleState
    f32     SpeedWalking
    f32     SpeedRunning
    f32     SpeedBerserk
    // Buffs
    u8      BuffCount
    for each buff:
        u32     SkillID
        u32     BuffUniqueID
        if hasAutoTransferEffect:
            bool IsCaster

    IF isPlayer:
        ascii   Name               // server: GetCharName()
        u8      JobType
        u8      JobLevel
        u8      PVPState           // PvPSTATE_*
        bool    IsRiding
        bool    InCombat
        if IsRiding: u32 RidingUniqueID
        u8      ScrollingType      // Reverse return, etc.
        u8      InteractionType    // 0=None, 1=OnStall, etc.
        u8      unkByte03          // server: possibly HwanLevel
        ascii   GuildName          // server: GetGuildName()
        if NOT hasJobMode:
            u32     GuildID
            ascii   GuildMemberName
            u32     GuildLastCrestRev
            u32     UnionID            // AllianceID
            u32     UnionLastCrestRev
            bool    IsFriendly
            u8      GuildMemberAuthority
        if InteractionType == OnStall:
            ascii   StallTitle
            u32     StallDecorationID
        u8      EquipmentCooldown
        u8      CaptureTheFlagType

    ELIF isNPC:
        u8      HasTalkOptions     // != 0
        if HasTalkOptions:
            u8      TalkOptionCount
            u8[]    TalkOptions
        if isMob:
            u8      MobType
            if ID4 == 2 || ID4 == 3:
                u8  Appearance
        elif isCOS:
            if NOT isHorse:
                if isAttackPet || isPickPet:
                    ascii PetName
                ascii   OwnerName
                u8      JobType
                if NOT isPickPet:
                    u8  PVPState
                if isGuildGuard:
                    u32 OwnerObjectID
                u32     OwnerUniqueID
        elif isFortressCos:
            u32     GuildID
            ascii   GuildName

    // Spawn-only trailer
    u8      unkByte02          // only for 0x3015, not groupspawn

ELIF isDrop(RefObjID):
    if isEquipable: u8 Plus
    elif isEtc:
        if isGold: u32 GoldAmount
        elif isQuest || isTradeGoods: ascii OwnerName
    u32     UniqueID
    u16     RegionID
    f32     PosX, PosY, PosZ
    u16     Angle
    bool    HasOwner
    if HasOwner: u32 OwnerJoinID
    u8      Rarity
    // Spawn-only trailer (not in groupspawn)
    u8      DropSourceType
    u32     DropUniqueID

ELIF isTeleport(RefObjID):
    u32     UniqueID
    u16     RegionID
    f32     PosX, PosY, PosZ
    u16     Angle
    u8      unkByte01
    u8      unkByte02
    u8      unkByte03
    u8      PortalType         // 0=Regular, 1=Dimensional
    if Regular:
        u32     unkUInt01
        u32     unkUInt02
    elif Dimensional:
        ascii   OwnerName
        u32     OwnerUniqueID
    if unkByte02 == 1:
        u32     unkUInt03      // STORE_OnONE_DEFAULT
        u8      unkByte04
```

### 0x303D — SERVER_CHARACTER_STATS_UPDATE

```
u32     PhyAtkMin
u32     PhyAtkMax
u32     MagAtkMin
u32     MagAtkMax
u16     PhyDefense
u16     MagDefense
u16     HitRate
u16     ParryRatio
u32     HPMax
u32     MPMax
u16     STR
u16     INT
```

### 0x3056 — SERVER_CHARACTER_EXPERIENCE_UPDATE

```
u32     SourceUniqueID     // entity that gave the exp
i64     ExpReceived        // can be negative (death penalty)
i64     SPExpReceived
// u8   unkByte01          // sometimes present
```

### 0x304E — SERVER_CHARACTER_INFO_UPDATE

```
u8      UpdateType
switch UpdateType:
    case 1:  u64 Gold
    case 2:  u32 SP
    case 4:  u8  BerserkPoints
```

### 0x3057 — SERVER_ENTITY_STATUS_UPDATE

```
u32     UniqueID
u8      unkByte01          // server: StatusFlags high byte?
u8      unkByte02          // server: StatusFlags low byte?
u8      UpdateType         // EntityStateUpdate enum
switch UpdateType:
    case 1 (HP):       u32 HP
    case 2 (MP):       u32 MP
    case 3 (HPMP):     u32 HP, u32 MP
    case 4 (BadStatus): u32 BadStatusFlags
    case 5 (EntityHPMP): u32 HP, u32 MP
```

### 0x30BF — SERVER_ENTITY_STATE_UPDATE

```
u32     UniqueID
u8      UpdateType
u8      UpdateState
// UpdateType values:
//   0 = LifeState    (LIFESTATE_*)
//   1 = MotionState  (MOTIONSTATE_*)
//   4 = GameState    (BATTLESTATE_*)
//   7 = PVPState     (PvPSTATE_*)
//   8 = InCombat     (0/1)
//   11 = ScrollingType
```

### 0xB070 — SERVER_ENTITY_SKILL_START

```
bool    Success
if Success:
    u8      CastType           // 0=Buff, 2=Attack
    u8      unkByte01          // server: skill execution flag?
    u32     SkillID
    u32     SourceUniqueID
    u32     SkillUniqueID
    u32     TargetUniqueID
    if CastType == Attack:
        DamageData (see below)
```

### 0xB071 — SERVER_ENTITY_SKILL_END

```
bool    Success
if Success:
    u32     SkillUniqueID
    u32     TargetUniqueID
    DamageData
```

### DamageData (shared sub-structure)

```
bool    HasDamage
if HasDamage:
    u8      HitCount
    u8      TargetCount        // AOE targets
    for each target:
        u32     TargetUniqueID
        u8      DamageEffect   // flags: 1=KnockBack, 2=Block, 4=Position, 8=Cancel, 128=Dead
        if DamageEffect == 128: (target died)
        elif (Block|Cancel): skip damage fields
        u8      DamageType     // flags: 1=Normal, 2=Critical, 4=Status
        u32     DamageValue
        u8      unkByte01      // server: possibly absorbed damage
        u8      unkByte02      // server: possibly reflected damage flag
        u8      unkByte03      // server: possibly status effect ID
```

### 0xB0BD — SERVER_ENTITY_SKILL_BUFF_ADDED

```
u32     TargetUniqueID
u32     SkillID
u32     BuffUniqueID
```

### 0xB072 — SERVER_ENTITY_SKILL_BUFF_REMOVED

```
bool    Success
if Success:
    u32     BuffUniqueID
```

### 0x30D0 — SERVER_ENTITY_SPEED_UPDATE

```
u32     UniqueID
f32     SpeedWalking
f32     SpeedRunning
```

### 0x30C8 — SERVER_PET_DATA

```
u32     UniqueID
u32     ModelID

// Branch based on COS type:

IF isHorse || isTransport:
    u32     HP
    u32     HPMax
    u8      InventoryCapacity
    if InventoryCapacity > 0:  // Transport
        u8      ItemCount
        for each:
            u8      Slot
            u32     RentableType
            u32     RefItemID
            u16     Quantity
            ascii   OwnerName
        // u32 OwnerUniqueID (unused)

ELIF isAttackPet:
    u32     HP
    u32     unkUInt01          // server: possibly HPMax
    u64     Exp
    u8      Level
    u16     HGP                // Hunger Gauge Points
    u32     SettingsFlags
    ascii   Name
    u8      unkByte03
    u32     OwnerUniqueID
    u8      unkByte04

ELIF isPickPet:
    u32     unkUInt01          // server: possibly HP
    u32     unkUInt02          // server: possibly HPMax
    u32     SettingsFlags
    ascii   Name
    u8      InventoryCapacity
    u8      ItemCount
    for each:
        u8      Slot
        ItemData
    // u32 OwnerUniqueID (unused)
```

### 0x30C9 — SERVER_PET_UPDATE

```
u32     UniqueID
u8      UpdateType
switch UpdateType:
    case 1: (Unsummoned - no data)
    case 3: (Exp)
        i64     ExpReceived
        u32     SourceUniqueID
    case 4: (Hungry)
        u16     HGP
    case 7: (Model changed on level up)
        u32     NewModelID
```

### 0x3065 — SERVER_PARTY_DATA

```
u32     unkUint01          // server: PartyID or PartyNumber
u32     unkUint02          // server: PartyLeaderJoinID?
u8      PurposeType
u8      SetupFlags
u8      PlayerCount
for each member:
    PartyMemberData (see below)
```

### PartyMemberData (shared sub-structure)

```
u8      unkByte01          // server: MemberType? (0=normal)
u32     MemberID           // JoinID
ascii   Name
u32     ModelID            // RefObjID
u8      Level
u8      HPMP               // packed: HP% in high nibble, MP% in low nibble
u16     RegionID
if inDungeon: i32 PosX/Y/Z
else: u16 PosX/Y/Z
u8      unkByte02          // server: possibly BodyMode
u8      unkByte03          // server: possibly LifeState
u8      unkByte04          // server: possibly MotionState
u8      unkByte05          // server: possibly GameState/BattleState
ascii   GuildName
u8      unkByte06          // server: possibly GuildMemberAuthority
// if SERVER_PARTY_UPDATE && unkByte02 == 2:
//     u8  unkByte07
u32     MasteryPrimaryID
u32     MasterySecondaryID
```

### 0x3864 — SERVER_PARTY_UPDATE

```
u8      UpdateType
switch UpdateType:
    case 1: (Dismissed)
        // u16 ErrorCode
    case 2: (Member joined)
        PartyMemberData
    case 3: (Member left)
        u32 MemberID
        // u8 Reason
    case 6: (Member update)
        u32     MemberID
        u8      MemberUpdateType
        switch MemberUpdateType:
            case 2: u8 Level
            case 4: u8 HPMP
            case 0x20: (Map position)
                u16     RegionID
                if inDungeon: i32 PosX/Y/Z
                else: u16 PosX/Y/Z
```

### 0x38F5 — SERVER_GUILD_UPDATE (31 code references — most complex update packet)

```
u8      UpdateType
// Many sub-types... (member join/leave/promote, notice change, GP update, etc.)
```

### 0x3101 — SERVER_GUILD_DATA (via 0x34B3 begin / 0x34B4 end)

```
u32     GuildID
ascii   GuildName
u8      GuildLevel
u32     GuildPoints
ascii   Notice
ascii   Message
u32     unkUInt00          // server: possibly UnionID/AllianceID
u8      unkByte00          // server: possibly GuildStorageSlots
u8      MemberCount
for each member:
    u32     MemberID           // CharID
    ascii   MemberName
    u8      unkByte01          // server: possibly MemberAuthority or online flag
    u8      Level
    u32     GuildPoints        // Member contribution
    u32     PermissionsFlags
    u32     unkUInt01          // server: possibly LastLoginTime
    u32     unkUInt02          // server: possibly DonateGP
    u32     unkUInt03          // server: possibly CharDBID
    ascii   Nickname           // server: GetNickName()
    u32     ModelID            // RefObjID
    bool    IsMaster
    bool    IsOffline
```

---

## 6. Item Structure (shared sub-structure for inventory items)

```
// Rentable Info (prefix)
u32     RentableType       // 0=None, 1=LimitedTime, 2=LimitedDistance, 3=Package
if LimitedTime:
    u16     CanDelete
    u32     PeriodBeginTime
    u32     PeriodEndTime
elif LimitedDistance:
    u16     CanDelete
    u16     CanRecharge
    u32     MeterRateTime
elif Package:
    u16     CanDelete
    u16     CanRecharge
    u32     PeriodBeginTime
    u32     PeriodEndTime
    u32     PackingTime

// Item Core
u32     RefItemID

IF isEquipable:
    u8      Plus               // Enhancement level (+1, +2, etc.)
    u64     Variance           // Random stat variance seed
    u32     Durability
    // Magic Options
    u8      MagicOptionCount
    for each:
        u32     OptionID
        u32     Value
    // Sockets
    u8      SocketFlag         // always 1
    u8      SocketCount
    for each:
        u8      SlotType
        u32     SocketID
        u32     Value
    // Advanced Elixirs
    u8      ElixirFlag         // always 2
    u8      ElixirCount
    for each:
        u8      SlotType
        u32     ElixirID
        u32     Value

ELIF isCoS (Companion scroll):
    IF isPet:
        u8      StateType      // 0=NeverSummoned, 1+=Active
        if StateType != NeverSummoned:
            u32     ModelID
            ascii   PetName
            if ID4 == 2: u32 PeriodEndTime
            u8      unkByte01
    ELIF isTransform:
        u32     ModelID
    ELIF isCube:
        u32     Quantity

ELIF isEtc:
    u16     Quantity
    if isAlchemy && (ID4 == 1 || ID4 == 2):
        u8  AssimilationProbability  // Magic/Attribute stone
    elif ID3 == 14 && ID4 == 2:     // Gacha card
        u8  ParamCount
        for each:
            u32 ParamID
            u32 Value
```

---

## 7. IGObj Interface Methods (160+ methods from assert strings)

### Core Identity
- `GetTypeID()`, `GetRefObjID()`, `GetGameID()`, `GetCharName()`, `SetCharName()`
- `GetNickName()`, `GetCodeName()`, `GetGuildName()`
- `GetJID()`, `GetLevel()`, `GetMaxLevel()`, `GetGender()`

### State
- `GetLifeState()`, `SetLifeState()`, `GetMotionState()`, `GetBodyMode()`, `SetBodyMode()`
- `GetJobState()`, `GetTeleportState()`, `SetCharacterState()`
- `GetCurHP()`, `GetCurMP()`, `ConsumeHpMp()`
- `IsPremiumItemPlayState()`

### Position & Movement
- `GetPosInfo()`, `SaveCurPosAsLastTelPosition()`
- `GetWorldID()`, `GetWorldLayerData()`, `SetWorldLayerData()`
- `EnterWorld()`, `LeaveWorldReq()`, `BanToDefaultWorld()`
- `AttachCustomTeleportCapability()`

### Combat & Skills
- `EngageBuffSkill()`, `IsActiveBuff()`, `GetRemainSkillPoint()`, `OffsetSkillPoint()`
- `IsTargeting()`, `GetCurSelectedObj()`, `IsAttackableCOS()`
- `NotifyClientAPIconStatus()`

### Inventory & Items
- `AddItem_EXT()`, `DelItem_EXT()`, `MutateItemAt()`
- `FindEmptySlotNum()`, `CountEmptyInventory()`, `ExpandInventory()`
- `CanBorrow()`, `CanDrop()`, `CanPick()`, `CanRepair()`, `CanSell()`, `CanThrow()`, `CanTrade()`, `CanUse()`
- `ForceDropItem()`, `InquireSameItem()`
- `IHaveCart()`, `IHaveMercenary()`, `IHaveTradeItem()`

### Item Type Checks
- `IsAccessory()`, `IsArmor()`, `IsArrow()`, `IsBolt()`, `IsBow()`, `IsBullet()`
- `IsCashItem()`, `IsContainerItem()`, `IsContainerSummonerItem()`
- `IsCrossBow()`, `IsElixir()`, `IsEquip()`, `IsExpendables()`
- `IsFreeBattleEquip()`, `IsGold()`, `IsHPPotion()`, `IsMPPotion()`, `IsPotion()`
- `IsItem()`, `IsRobe()`, `IsScroll()`, `IsShield()`, `IsSpecialty()`
- `IsSummonScroll()`, `IsWeapon()`, `IsVehicle()`

### Entity Type Checks
- `IsChar()`, `IsPC()`, `IsNPC()`, `IsNPCNPC()`, `IsMonster()`
- `IsCOS()`, `IsMercenary()`, `IsPet()`, `IsCart()`
- `IsStruct()`, `IsTeleportGate()`, `IsTownPortal()`
- `IsCatchMob()`, `IsChinsTombMonster()`, `IsPartySupportMonster()`
- `IsReinforceProbUP()`, `IsReinforceRecipe()`
- `IsQuest_n_EventItem()`, `IsQuestByCompositeItem()`

### Quest System
- `GetQuestData()`, `GetQuestStatus()`, `GetQuestStatusByName()`
- `GetQuestAchievementCount()`, `SetQuestAchievementCount()`, `AddQuestAchievementCount()`
- `GetQuestEndDate()`, `GetRecvQuestCount()`
- `UpdateQuestStatus()`, `UpdateQuestNpcID()`, `UpdateQuestContentsString()`, `UpdateQuestStartDataAll()`, `UpdateQuestTimeLimit()`
- `PrepareQuestData()`, `PrepareClosedQuestData()`
- `SaveQuestNow()`, `SaveClearQuestNow()`, `ResetQuestBlock()`
- `SendQuestCatchMobResult()`, `SendQuestEventMessage()`, `SendQuestNpcChat()`, `SendQuestStartTimeBar()`
- `SearchHaveCatchMob()`, `DeleteCatchCOS()`, `DeleteMobForCatchQuest()`
- `SpawnCatchCOSForCatchQuest()`, `UseQuestByCompositeItem()`
- `GetMaxCountOfQuestByCompositeItem()`, `GetRemainCountOfQuestByCompositeItem()`
- `RefreshEventGuideData()`, `GetVolatileEventData()`, `GetVolatileQuestData()`
- `IsAccomplishedCollectionBook_Theme()`, `IsRegisteredCollectionBook_Item()`

### NPC Interaction
- `EnableTalkMenuItem()`, `RegisterTalkMenuItem()`, `SetTalkMenuTitle()`
- `ShowFirstTalkMenu()`, `ShowMenu()`, `ShowRewardWindow()`, `TerminateMenu()`
- `IsFirstTalkMenuEnable()`, `GetMenuContext()`
- `EnterScriptMode()`, `AddAvailableInteraction()`, `SetAvailableInteractionPerGObj()`
- `IsInteractionAble()`, `RegisterNPCInteractionBlock()`, `UnregisterNPCInteractionBlock()`

### Guild/Union
- `CompareMyAndGuildMaster()`, `CompareGold()`, `OffsetGold()`
- `GetPCGuildMemberAverageLevel()`, `GetPCGuildMemberHighestLevel()`

### Events & World
- `ActivateAI()`, `RaiseEvent()`, `RaiseEventSingle()`
- `RegisterEventHandler()`, `UnregisterEventHandler()`
- `GetEventHandlers()`, `GetWorldLayerEventHandlers()`
- `GetEventResultInfo()`, `SetEventResult()`, `SetEventResultInfo()`
- `RegisterSpot_Object()`, `RegisterSpot_Position()`, `UnregisterSpot()`, `UnregisterSpotByQuest()`
- `GetInsDungeonInfo()`, `SetInsDungeonInfo()`, `GetInstanceWorldUsers()`
- `BackupData()`, `CanRevive()`, `OffsetExpPoint()`
- `UpdateHwanLevel()`, `REH_OnTrapped()`, `Zoe()`

### Messaging
- `AllocMsgForPeer()`, `SendMsgToPeer()`, `OutputChatMsg()`
- `ChattingByProxy()`, `ChattingByProxyArg()`
- `AddDisplayEffect()`, `SetChangeObjActiveState()`

### Trigger Actions (from CGEventDaemon)
```
CGameTriggerAction_CREATEOBJECT_STRUCT
CGameTriggerAction_CREATEOBJECT_TELEPORT
CGameTriggerAction_MESSAGE_NOTIFY_WINDOW
CGameTriggerAction_MESSAGE_SYSTEM_WINDOW
CGameTriggerAction_MONSTER_ACTIVE_NEST
CGameTriggerAction_MONSTER_LOAD_MONSTER
CGameTriggerAction_SWITCH_EVENTZONE
CGameTriggerAction_SWITCH_TELEPORT
CGameTriggerAction_SWITCH_TRIGGER
CGameTriggerAction_VARIABLE_ADDITION
CGameTriggerAction_VARIABLE_SUBTRACTION
CGameTriggerAction_VARIABLE_VALUE
```

---

## 8. Database Schema (from SQL Strings)

### Tables Referenced

| Table | Purpose |
|-------|---------|
| `_Inventory` | Character inventory (CharID, Slot, ItemID) |
| `_InventoryForAvatar` | Avatar equipment (CharID, Slot, ItemID) |
| `_InventoryForLinkedStorage` | Linked storage items |
| `_InventoryForMagicCube` | Magic cube items |
| `_InvCOS` | COS inventory (COSID, Slot, ItemID) |
| `_EquipInvCos` | COS equipment |
| `_Chest` | Personal storage (UserJID, Slot, ItemID) |
| `_GuildChest` | Guild storage (GuildID, Slot, ItemID) |
| `_TempChest` | Temporary storage |
| `_ITEMS` | Item instances (ID64, properties) |
| `_BindingOptionWithItem` | Item magic options (nItemDBID) |
| `_RentItemInfo` | Rental item data (nItemDBID, period, etc.) |
| `_OpenMarket` | Consignment shop |
| `_CHARCOS` | Character COS data (OWNERCHARID) |
| `_CharCollectionBook` | Collection book progress (CharID) |
| `_CharInstanceWorldData` | Instance dungeon data |
| `_CharTrijob` | Trade job data |
| `_CharTrijobSafeTrade` | Safe trade data |
| `_Friend` | Friends list |
| `_BlockedWhisperers` | Blocked whisper list |
| `_ClientConfig` | Client settings |
| `_QuickSlotData` | Hotkey/quickslot data |
| `_SiegeFortress` | Fortress ownership |
| `_SiegeFortressObject` | Fortress objects |
| `_SiegeFortressStruct` | Fortress structures |
| `_SiegeFortressRequest` | Siege requests |
| `_SiegeFortressBattleRecord` | Battle history |
| `_SiegeFortressItemForge` | Fortress item forging |
| `_SiegeFortressStoneState` | Seal stone status |
| `_GPHistory` | Guild point history |
| `_ServerEvent` | Active server events |
| `_ServerEventReward` | Event rewards |
| `_ShopItemStockQuantity` | Shop stock |
| `_LogSchedule` | Schedule logs |
| `_AssociationReputation` | Reputation data |
| `_TradeBagInventory` | Trade bag items |
| `_SupportGoldConfig` | Gold support config |

### Key Stored Procedures

| Procedure | Parameters | Purpose |
|-----------|------------|---------|
| `_STRG_ADD_EQUIP_NORMAL` | (?, ?, slot, storageType, refID, plus, variance, durability, count) | Add equipment to storage |
| `_STRG_ADD_EXPENDABLE` | (?, ?, slot, storageType, refID, quantity, count) | Add consumable |
| `_STRG_ADD_SPECIALTY` | (?, ?, slot, storageType, refID, ..., ownerName) | Add trade goods |
| `_STRG_ADD_ALCHEMYSTONE` | (?, ?, slot, storageType, refID, ...) | Add alchemy stone |
| `_STRG_ADD_ITEM_MAGIC` | (?, ?, slot, storageType, refID, plus, variance, durability, count, ...) | Add magic item |
| `_STRG_MOVE_ITEM` | (charID, srcSlot, dstSlot, ...) | Move item between slots |
| `_STRG_SWAP_ITEM` | (charID, slot1, slot2, ...) | Swap two items |
| `_STRG_DEL_ITEM` | (charID, itemDBID, slot, ...) | Delete item |
| `_STRG_MERGE_ITEM` | (charID, slot1, slot2, ...) | Stack merge |
| `_STRG_SPLIT_ITEM` | (?, ?, charID, slot, ...) | Stack split |
| `_AddNewCOS` | (ownerCharID, modelID, ..., date) | Create new COS |
| `_ChangeCOSState` | (cosID, state) | Change COS state |
| `_COS_Naming` | (cosID, name) | Name a pet |
| `_DeleteCharCOS` | (charID, cosID, type) | Delete COS |
| `_OpenMarket_Insert` | (charID, ?, count, ..., price, fee, ..., dates, ...) | List item |
| `_OpenMarket_Purchase` | (buyerCharID, sellerCharID, ?, ..., price, count, date) | Buy item |
| `_OpenMarket_Cancle` | (charID, ..., itemDBID) | Cancel listing |
| `_SiegeFortressRequestSiege` | (fortressID, guildID, ...) | Request siege |
| `_SiegeFortressFinished` | (fortressID) | End siege |
| `_SiegeFortressTaxCollect` | (fortressID, guildID, gold) | Collect tax |
| `_SiegeFortressHireNPC` | (fortressID, ...) | Hire fortress NPC |
| `_AssignNickName` | (charID, name) | Set guild nickname |
| `_ADDTIMEDJOB` | (charID, ..., params, ..., itemDBID, ...) | Add timed job |
| `_Bind_Option_Manager` | (charID, itemDBID, ...) | Manage binding options |
| `_Rent_Info_Manager` | (charID, itemDBID, ..., dates, ...) | Manage rental items |
| `_Guild_Master_Election_Available` | (guildID, ...) | Check election |
| `_ADDLOGCHAR` | (charID, type, ..., name, info) | Character event log |
| `_ADDLOGITEM` | (charID, type, itemDBID, ..., names, ..., gold) | Item event log |
| `_ADDLOGSIEGEFORTRESS` | (fortressID, type, ..., info) | Siege event log |

---

## 9. AgentServer Analysis

The AgentServer acts as a relay/proxy between clients and the GameServer.

### Key Strings
```
FRAMEWORKMSG_REGISTER_CONTENT_USER_ACK
FRAMEWORKMSG_REGISTER_SHARD_USER_ACK
RELAY_MSG_TO_CLIENT_MULTI_DATA : realmsgid is null or target is empty
RELAY_MSG_TO_CLIENT_MULTI_LIST failed : realmsgid is different [0x%X] - [0x%X]
Traffic Filter Configuration [%u Packets / %u ms]
XTrap_S_RecvGamePacket / XTrap_S_SendGamePacket
```

### Classes
```
ServerFramework::CServerProcessMain
CSession / charNode / pcharNode
COverlapJob_RelayMsg
COverlapJob_InitializeLocalData
CMassiveMsg
```

### Source Files Referenced
```
D:\WORK2005\Source\Common\Framework\MassiveMsg.cpp
D:\WORK2005\Source\JMX_ServerFramework\ServerFramework\ServerMoniterView.cpp
```

---

## 10. Existing Documentation Corrections

The existing `docs/messages/` files were generated from **client binary** (sro_client.exe) analysis. Many opcode-to-name mappings are incorrect:

| Opcode | Current (wrong) Name | Correct Name |
|--------|---------------------|---------------------|
| 0x3015 | SERVER_CHARACTER_DELETE_RESPONSE | SERVER_ENTITY_SPAWN |
| 0x3013 | SERVER_CHARACTER_CREATE_RESPONSE | SERVER_CHARACTER_DATA |
| 0x303D | SERVER_ENTITY_SPAWN | SERVER_CHARACTER_STATS_UPDATE |
| 0x3056 | SERVER_ENTITY_UPDATE_MOVEMENT | SERVER_CHARACTER_EXPERIENCE_UPDATE |
| 0x304E | SERVER_ENTITY_UPDATE_STATE | SERVER_CHARACTER_INFO_UPDATE |
| 0x30BF | SERVER_NPC_RESPONSE | SERVER_ENTITY_STATE_UPDATE |
| 0x30C8 | SERVER_EXCHANGE_START | SERVER_PET_DATA |
| 0x30C9 | SERVER_EXCHANGE_CONFIRM | SERVER_PET_UPDATE |
| 0x3101 | SERVER_NOTICE_CLEAR | SERVER_GUILD_DATA |
| 0x3864 | SERVER_WORLD_UPDATE | SERVER_PARTY_UPDATE |
| 0xB070 | CLIENT_ENTITY_POSITION_REQUEST | SERVER_ENTITY_SKILL_START |
| 0xB071 | CLIENT_ENTITY_DETAIL_REQUEST | SERVER_ENTITY_SKILL_END |
| 0xB072 | CLIENT_ENTITY_STATUS_REQUEST | SERVER_ENTITY_SKILL_BUFF_REMOVED |
| 0xB0BD | CLIENT_STORAGE_REQUEST | SERVER_ENTITY_SKILL_BUFF_ADDED |

These should be regenerated using the corrected opcode map from this analysis.

---

## 11. Server Log Field Name Cross-Reference

Server log format strings reveal authoritative field names for packet fields previously marked as "unk":

| Original "unk" Field | Server Field Name | Context |
|-------------------|-------------------|---------|
| `unkByte04` (CharData states) | `BodyMode` | `GetBodyMode()` — BODYMODE_NORMAL/HWAN/BERSERKER/INVINCIBLE/INVISIBLE |
| `GameState` | `BattleState` | BATTLESTATE_IN_PEACE / BATTLESTATE_IN_BATTLE |
| `unkByte01` (spawn) | `BodyMode` | Same as above |
| `unkByte03` (player spawn) | `HwanLevel` | `UpdateHwanLevel()` IGObj method |
| PartyMember `unkByte02-05` | BodyMode, LifeState, MotionState, BattleState | Same state fields as entity spawn |
| PartyMember `unkByte06` | GuildMemberAuthority | `GUILD_MEMBER_INFO` struct field |
| Guild `unkUInt00` | UnionID/AllianceID | from `_AssociationReputation`, `AllianceID[%d]` strings |
| Guild `unkByte00` | GuildStorageSlots | storage capacity |
| GuildMember `unkByte01` | MemberClass/Race | character race or class indicator |
| GuildMember `unkUInt01` | LastLoginTime | timestamp |
| GuildMember `unkUInt02` | DonateGP | guild point donations |
| GuildMember `unkUInt03` | CharDBID | character database ID |
| StatusUpdate `unkByte01/02` | StatusTargetType, StatusSourceType | damage source/target flags |
| SkillStart `unkByte01` | SkillExecutionMode | skill execution flag |
| DamageData `unkByte01-03` | AbsorbedDamage, ReflectedFlag, StatusEffectID | combat calculation results |
| PetData `unkUInt01` (attack) | HPMax | pet max HP |
| PetData `unkByte03` (attack) | PetLevel or HGP flag | |
| PetData `unkByte04` (attack) | OwnerJobType | trade job type of owner |
| PetData `unkUInt01/02` (pick) | HP, HPMax | pick pet health values |

---

## Decompiled Handler Statistics

All 295 unique message handler functions have been decompiled to C pseudocode using the r2ghidra decompiler.

### Decompilation Metrics

| Metric | Value |
|--------|-------|
| Total handlers decompiled | 295 |
| Total lines of C pseudocode | 26,328 |
| Handlers with conditional reads | 181 |
| Handlers with loop reads | 41 |
| Total Stream::Read calls found | 1,152 |
| Unique function calls identified | 869 |
| Shared functions (3+ handlers) | 121 |

### Key Functions Identified

#### Message I/O

| Address | Function | Purpose |
|---------|----------|---------|
| `0x004F7220` | `Stream::Read` | Generic read: `Read(dest, size)` |
| `0x004B3B40` | `ReadByte` | Read 1 byte (u8) |
| `0x004D2820` | `ReadWord` | Read 2 bytes (u16) |
| `0x004B3BA0` | `ReadDword` | Read 4 bytes (u32) |
| `0x004B3C00` | `ReadQword` | Read 8 bytes (u64) |
| `0x004AF830` | `ReadBytes` | Read N bytes |
| `0x004EEA40` | `ReadFloat` | Read 4-byte float |
| `0x0053CEA0` | `CMsgStreamBuffer::Init` | Initialize outgoing message |
| `0x00508FE0` | `CMsgStreamBuffer::Write` | Write to outgoing message |
| `0x008418D0` | `CSession::Send` | Send message |
| `0x005097A0` | `CMsgStreamBuffer::Destroy` | Cleanup message buffer |

#### Most-Called Shared Functions

| Address | Called By | Likely Purpose |
|---------|----------|----------------|
| `0x00778190` | 118 handlers | Show system message / notification |
| `0x00B42C6D` | 94 handlers | Stack security check (`__security_check_cookie`) |
| `0x008C9C30` | 72 handlers | UI string resource lookup |
| `0x007781B0` | 49 handlers | Display colored notification |
| `0x0046ED50` | 39 handlers | String operation (copy/set) |
| `0x00798D00` | 36 handlers | Entity manager operation |
| `0x004F7A70` | 32 handlers | Stream buffer operation |
| `0x009C3220` | 28 handlers | Entity lookup by unique ID |
| `0x0077B580` | 28 handlers | UI update / refresh |
| `0x0049D640` | 27 handlers | Debug logging |

#### Assert Function

| Address | Function | Purpose |
|---------|----------|---------|
| `0x0049E490` | `Assert` | Debug assert with source file + expression |

Assert calls reveal original variable names and source files:

- `g_pMyPlayerObj->GetJobType() == byJobType`
- `!m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedSkill(dwSkillID)`
- `m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)`

### Common Handler Patterns

#### Result-Branching Pattern

Most client-response handlers follow this pattern:

```c
void handler(void) {
    Stream::Read(&byResult, 1);    // Read result byte

    if (byResult == 1) {
        // SUCCESS: read additional data fields
        Stream::Read(&dwData, 4);
        Stream::Read(&wParam, 2);
        // ... process data ...
        ShowMessage(L"UIIT_MSG_SUCCESS");
    }
    else if (byResult == 2) {
        // FAILURE: read error code
        Stream::Read(&wErrorCode, 2);
        ShowMessage(L"UIIT_MSG_FAIL");
    }
}
```

#### Loop-Read Pattern

Used for variable-length lists (party members, guild members, items):

```c
Stream::Read(&byCount, 1);
for (int i = 0; i < byCount; i++) {
    Stream::Read(&dwMemberUID, 4);
    Stream::Read(&byLevel, 1);
    Stream::Read(&wHP, 2);
    // ... per-member data ...
}
```

#### Type-Dispatch Pattern

Used for multi-purpose handlers:

```c
Stream::Read(&byType, 1);
switch (byType) {
    case 1:  // Type A
        Stream::Read(&fieldA, 4);
        break;
    case 2:  // Type B
        Stream::Read(&fieldB1, 4);
        Stream::Read(&fieldB2, 2);
        break;
}
```

### Original Source Files

The following original source files are referenced in assert strings:

| Source File | Handler Domain |
|-------------|----------------|
| `NetProcessInInterface.cpp` | UI/Interface message handling |
| `NetProcessInObject.cpp` | Game object updates |
| `NetProcessInInner.cpp` | Core/inner game logic |
| `NetProcessInNavAndSkill.cpp` | Navigation & skill processing |
| `IFMainPopup.cpp` | Main popup interface |
| `IFStall.cpp` | Stall/shop interface |
| `IF_NPCTalk.cpp` | NPC dialog interface |
| `NIFGuildWnd.cpp` | Guild window interface |
| `CharacterDependentData.cpp` | Character data management |
| `GlobalDataManager.cpp` | Global game data |
| `COSDataMgr.cpp` | COS (pet/transport) data |
| `IGIDObject.cpp` | GID object management |

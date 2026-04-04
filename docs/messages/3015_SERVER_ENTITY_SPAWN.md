# SERVER_ENTITY_SPAWN

> **Corrected name** (server RE): Was `SERVER_CHARACTER_DELETE_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3015` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A9100` |

### Fields (Server RE)

Top-level branching based on `RefObjID` type lookup:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `RefObjID` | `u32` | 4 | Object reference ID (determines branch) |

---

#### Branch: isSkillZone

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `EntityTypeCode` | `u16` | 2 | Constant `0x0054` — hardcoded zone-entity type identifier written by `CGSkillObject` spawn serializer at VA `0x48CE79` (`push 0x54; call 0x48bee0`) |
| 3 | `SkillID` | `u32` | 4 | Skill creating the zone |
| 4 | `UniqueID` | `u32` | 4 | Zone unique ID |
| 5 | `RegionID` | `u16` | 2 | Map region |
| 6 | `PosX, PosY, PosZ` | `f32` | 12 | Position |
| 7 | `Angle` | `u16` | 2 | Facing angle |

---

#### Branch: isModel (Players, NPCs, Mobs, COS, Fortress Structures)

**Player-specific prefix:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `Scale` | `u8` | 1 | Character scale |
| 3 | `BerserkLevel` | `u8` | 1 | Berserk mode level |
| 4 | `PVPCapeType` | `u8` | 1 | PVP cape visual |
| 5 | `ExpIconType` | `u8` | 1 | Experience icon |
| 6 | `EquipMaxCapacity` | `u8` | 1 | (seems unused) |
| 7 | `EquipCount` | `u8` | 1 | Equipped items |

For each equip: `u32 RefItemID`, if isEquipable: `u8 Plus`

| 8 | `AvatarMaxCapacity` | `u8` | 1 | |
| 9 | `AvatarCount` | `u8` | 1 | Avatar items |

For each avatar: `u32 RefItemID`, if isEquipable: `u8 Plus`

| 10 | `HasMask` | `bool` | 1 | Transform active |

If `HasMask`: `u32 MaskRefObjID`, if same model type: `u8 MaskScale, u8 MaskEquipCount, u32[] MaskEquipIDs`

**Fortress Structure prefix (isNPC && isFortressStruct):**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `HP` | `u32` | 4 | Structure HP |
| 3 | `RefEventStructID` | `u32` | 4 | Event structure ref |
| 4 | `State` | `u16` | 2 | Structure state |

**All models — Position:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `UniqueID` | `u32` | 4 | Entity unique ID |
| - | `RegionID` | `u16` | 2 | Map region |
| - | `PosX, PosY, PosZ` | `f32` | 12 | Position |
| - | `Angle` | `u16` | 2 | Facing angle |
| - | `HasMovement` | `bool` | 1 | Is moving |
| - | `MovementSpeedType` | `u8` | 1 | Walk/Run |

If `HasMovement`:
- If dungeon: `u16 DestRegion, i32 DestX/Y/Z`
- Else: `u16 DestRegion, u16 DestX/Y/Z`

If NOT moving: `u8 MovementActionType, u16 Angle`

**All models — States:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `LifeState` | `u8` | 1 | GetLifeState() |
| - | `BodyMode` | `u8` | 1 | `BODYMODE_*` enum — `GetBodyMode()` (confirmed from `BUF_CHARACTER_STATUS` RTTI) |
| - | `MotionState` | `u8` | 1 | GetMotionState() |
| - | `GameState` | `u8` | 1 | BattleState |
| - | `SpeedWalking` | `f32` | 4 | Walking speed |
| - | `SpeedRunning` | `f32` | 4 | Running speed |
| - | `SpeedBerserk` | `f32` | 4 | Berserk speed |

**All models — Buffs:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `BuffCount` | `u8` | 1 | Active buffs |

For each buff: `u32 SkillID, u32 BuffUniqueID`, if hasAutoTransferEffect: `bool IsCaster`

**Player suffix:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `Name` | `ascii` | var | GetCharName() |
| - | `JobType` | `u8` | 1 | 0=None, 1=Trader, 2=Thief, 3=Hunter |
| - | `JobLevel` | `u8` | 1 | Trade job level |
| - | `PVPState` | `u8` | 1 | PvPSTATE_* |
| - | `IsRiding` | `bool` | 1 | On mount |
| - | `InCombat` | `bool` | 1 | In battle |
| - | `RidingUniqueID` | `u32` | 4 | Only if IsRiding |
| - | `ScrollingType` | `u8` | 1 | Reverse return etc. |
| - | `InteractionType` | `u8` | 1 | 0=None, 1=OnStall, etc. |
| - | `HwanLevel` | `u8` | 1 | Hwan transformation level — `UpdateHwanLevel()` method (confirmed from server log analysis) |
| - | `GuildName` | `ascii` | var | GetGuildName() |

If NOT hasJobMode:

| Name | Type | Description |
|------|------|-------------|
| `GuildID` | `u32` | Guild ID |
| `GuildMemberName` | `ascii` | Guild member name |
| `GuildLastCrestRev` | `u32` | Crest revision |
| `UnionID` | `u32` | Alliance ID |
| `UnionLastCrestRev` | `u32` | Alliance crest revision |
| `IsFriendly` | `bool` | Friendly flag |
| `GuildMemberAuthority` | `u8` | Guild rank/authority |

If `InteractionType == OnStall`:

| Name | Type | Description |
|------|------|-------------|
| `StallTitle` | `ascii` | Stall title |
| `StallDecorationID` | `u32` | Stall decoration |

| - | `EquipmentCooldown` | `u8` | 1 | |
| - | `CaptureTheFlagType` | `u8` | 1 | CTF type |

**NPC suffix:**

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `HasTalkOptions` | `u8` | 1 | != 0 means has options |

If `HasTalkOptions`: `u8 TalkOptionCount, u8[] TalkOptions`

If `isMob`:
- `u8 MobType`
- If `ID4 == 2 || ID4 == 3`: `u8 Appearance`

If `isCOS` and NOT `isHorse`:
- If isAttackPet/isPickPet: `ascii PetName`
- `ascii OwnerName, u8 JobType`
- If NOT isPickPet: `u8 PVPState`
- If isGuildGuard: `u32 OwnerObjectID`
- `u32 OwnerUniqueID`

If `isFortressCos`: `u32 GuildID, ascii GuildName`

**Spawn trailer (only for 0x3015, not groupspawn):**
`u8 SpawnCategory` — sourced from 3rd argument of sender function `0x533f70` (`[ebp+0x10]`); values 5 and 6 trigger additional player-specific data in the send path

---

#### Branch: isDrop

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | (varies) | — | — | If isEquipable: `u8 Plus` |

If isEtc:
- If isGold: `u32 GoldAmount`
- If isQuest/isTradeGoods: `ascii OwnerName`

| - | `UniqueID` | `u32` | 4 | Drop unique ID |
| - | `RegionID` | `u16` | 2 | Map region |
| - | `PosX, PosY, PosZ` | `f32` | 12 | Position |
| - | `Angle` | `u16` | 2 | Facing angle |
| - | `HasOwner` | `bool` | 1 | Has pickup restriction |
| - | `OwnerJoinID` | `u32` | 4 | Only if HasOwner |
| - | `Rarity` | `u8` | 1 | Drop rarity |

Spawn trailer: `u8 DropSourceType, u32 DropUniqueID`

---

#### Branch: isTeleport

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `UniqueID` | `u32` | 4 | Teleport unique ID |
| 3 | `RegionID` | `u16` | 2 | Map region |
| 4 | `PosX, PosY, PosZ` | `f32` | 12 | Position |
| 5 | `Angle` | `u16` | 2 | Facing angle |
| 6 | `PortalState` | `u8` | 1 | Byte 0 of sub-object at `[entity+0x30]`; active/inactive state of the portal |
| 7 | `QuestFlags` | `u8` | 1 | Byte 1 of sub-object at `[entity+0x30]`; quest-related visibility flags |
| 8 | `LevelRestriction` | `u8` | 1 | From `[entity+0x15e]`; minimum level required to use portal |
| 9 | `PortalType` | `u8` | 1 | From `[entity+0x15f]`; `6`=Dimensional, any other value=Regular |

If Regular (`PortalType != 6`): `u32 DestRegionID` (from `[entity+0x160]`), `u32 DestPortalID` (from `[entity+0x164]`)
If Dimensional (`PortalType == 6`): `ascii DestinationName` (from `[entity+0x168]`), `u32 DestinationID` (from `[entity+0x164]`)

> **Note**: Some third-party tools show a conditional `if unkByte02 == 1` block with extra fields here. This conditional **does not exist** in the server binary (`CGObjStruct` serializer `0x52F000`). The server writes exactly 4 bytes (PortalState, QuestFlags, LevelRestriction, PortalType) then the type-specific block.

### Structure Summary

```
  RefObjID                             u32

  IF isSkillZone:
    EntityTypeCode                     u16  // constant 0x0054 (hardcoded by CGSkillObject)
    SkillID                            u32
    UniqueID                           u32
    RegionID, PosX/Y/Z, Angle         u16, f32x3, u16

  ELIF isModel:
    IF isPlayer:
      Scale, BerserkLevel              u8, u8
      PVPCapeType, ExpIconType         u8, u8
      Equipment + Avatar inventories   (variable)
      HasMask + mask data              (variable)
    ELIF isFortressStruct:
      HP, RefEventStructID, State      u32, u32, u16

    // All models:
    UniqueID, RegionID, Pos, Angle     u32, u16, f32x3, u16
    Movement data                      (variable)
    LifeState, BodyMode, MotionState, GameState   u8x4    // BodyMode = BODYMODE_*
    SpeedWalking/Running/Berserk       f32x3
    Buffs                              (variable)

    IF isPlayer:
      Name, JobType, JobLevel, PVPState, ...
      Guild data, Stall data           (variable)
    ELIF isNPC:
      TalkOptions, Mob/COS data        (variable)

    SpawnCategory (spawn trailer)      u8   // 5 or 6 = player-specific handling

  ELIF isDrop:
    Item type data (Plus/Gold/Owner)   (variable)
    UniqueID, Region, Pos, Angle       u32, u16, f32x3, u16
    HasOwner, [OwnerJoinID], Rarity    bool, [u32], u8
    DropSourceType, DropUniqueID       u8, u32

  ELIF isTeleport:
    UniqueID, Region, Pos, Angle       u32, u16, f32x3, u16
    PortalState, QuestFlags            u8x2  // bytes 0-1 of *[entity+0x30]
    LevelRestriction                   u8    // [entity+0x15e]
    PortalType                         u8    // [entity+0x15f]; 6=Dimensional, else=Regular
    IF PortalType == 6 (Dimensional):
      DestinationName                  ascii // [entity+0x168]
      DestinationID                    u32   // [entity+0x164]
    ELSE (Regular):
      DestRegionID                     u32   // [entity+0x160]
      DestPortalID                     u32   // [entity+0x164]
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpawnSkillzone {
        uint16_t EntityTypeCode;
        uint32_t SkillID;
        uint32_t UniqueID;
        uint16_t RegionID;
        float PosX;
        float PosY;
        float PosZ;
        uint16_t Angle;
    };
    struct EntitySpawnModel {
        uint8_t Scale;
        uint8_t BerserkLevel;
        uint8_t PVPCapeType;
        uint8_t ExpIconType;
        uint8_t EquipMaxCapacity;
        uint8_t EquipCount;
        uint32_t HP;
        uint32_t RefEventStructID;
        uint16_t State;
        uint32_t UniqueID;
        uint16_t RegionID;
        float PosX;
        float PosY;
        float PosZ;
        uint16_t Angle;
        bool HasMovement;
        uint8_t MovementSpeedType;
        uint8_t LifeState;
        uint8_t BodyMode;
        uint8_t MotionState;
        uint8_t GameState;
        float SpeedWalking;
        float SpeedRunning;
        float SpeedBerserk;
        uint8_t BuffCount;
        std::string Name;
        uint8_t JobType;
        uint8_t JobLevel;
        uint8_t PVPState;
        bool IsRiding;
        bool InCombat;
        uint32_t RidingUniqueID;  // conditional
        uint8_t ScrollingType;
        uint8_t InteractionType;
        uint8_t HwanLevel;
        std::string GuildName;
        uint32_t GuildID;
        std::string GuildMemberName;
        uint32_t GuildLastCrestRev;
        uint32_t UnionID;
        uint32_t UnionLastCrestRev;
        bool IsFriendly;
        uint8_t GuildMemberAuthority;
        std::string StallTitle;
        uint32_t StallDecorationID;
        uint8_t HasTalkOptions;
    };
    struct EntitySpawnDrop {
        uint8_t varies;  // conditional
    };
    struct EntitySpawnTeleport {
        uint32_t UniqueID;
        uint16_t RegionID;
        float PosX;
        float PosY;
        float PosZ;
        uint16_t Angle;
        uint8_t PortalState;
        uint8_t QuestFlags;
        uint8_t LevelRestriction;
        uint8_t PortalType;
    };
    struct EntitySpawn {
        uint32_t RefObjID;
        std::variant<EntitySpawnSkillzone, EntitySpawnModel, EntitySpawnDrop, EntitySpawnTeleport> body;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public abstract record EntitySpawnBody;
    public record EntitySpawnSkillzone(ushort EntityTypeCode, uint SkillID, uint UniqueID, ushort RegionID, float PosX, float PosY, float PosZ, ushort Angle) : EntitySpawnBody;
    public record EntitySpawnModel(byte Scale, byte BerserkLevel, byte PVPCapeType, byte ExpIconType, byte EquipMaxCapacity, byte EquipCount, uint HP, uint RefEventStructID, ushort State, uint UniqueID, ushort RegionID, float PosX, float PosY, float PosZ, ushort Angle, bool HasMovement, byte MovementSpeedType, byte LifeState, byte BodyMode, byte MotionState, byte GameState, float SpeedWalking, float SpeedRunning, float SpeedBerserk, byte BuffCount, string Name, byte JobType, byte JobLevel, byte PVPState, bool IsRiding, bool InCombat, uint RidingUniqueID, byte ScrollingType, byte InteractionType, byte HwanLevel, string GuildName, uint GuildID, string GuildMemberName, uint GuildLastCrestRev, uint UnionID, uint UnionLastCrestRev, bool IsFriendly, byte GuildMemberAuthority, string StallTitle, uint StallDecorationID, byte HasTalkOptions) : EntitySpawnBody;
    public record EntitySpawnDrop(byte varies) : EntitySpawnBody;
    public record EntitySpawnTeleport(uint UniqueID, ushort RegionID, float PosX, float PosY, float PosZ, ushort Angle, byte PortalState, byte QuestFlags, byte LevelRestriction, byte PortalType) : EntitySpawnBody;
    public record EntitySpawn(uint RefObjID, EntitySpawnBody Body);
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpawnSkillzone {
        pub entity_type_code: u16,
        pub skill_id: u32,
        pub unique_id: u32,
        pub region_id: u16,
        pub pos_x: f32,
        pub pos_y: f32,
        pub pos_z: f32,
        pub angle: u16,
    }
    pub struct EntitySpawnModel {
        pub scale: u8,
        pub berserk_level: u8,
        pub pvpcape_type: u8,
        pub exp_icon_type: u8,
        pub equip_max_capacity: u8,
        pub equip_count: u8,
        pub hp: u32,
        pub ref_event_struct_id: u32,
        pub state: u16,
        pub unique_id: u32,
        pub region_id: u16,
        pub pos_x: f32,
        pub pos_y: f32,
        pub pos_z: f32,
        pub angle: u16,
        pub has_movement: bool,
        pub movement_speed_type: u8,
        pub life_state: u8,
        pub body_mode: u8,
        pub motion_state: u8,
        pub game_state: u8,
        pub speed_walking: f32,
        pub speed_running: f32,
        pub speed_berserk: f32,
        pub buff_count: u8,
        pub name: String,
        pub job_type: u8,
        pub job_level: u8,
        pub pvpstate: u8,
        pub is_riding: bool,
        pub in_combat: bool,
        pub riding_unique_id: u32,  // conditional
        pub scrolling_type: u8,
        pub interaction_type: u8,
        pub hwan_level: u8,
        pub guild_name: String,
        pub guild_id: u32,
        pub guild_member_name: String,
        pub guild_last_crest_rev: u32,
        pub union_id: u32,
        pub union_last_crest_rev: u32,
        pub is_friendly: bool,
        pub guild_member_authority: u8,
        pub stall_title: String,
        pub stall_decoration_id: u32,
        pub has_talk_options: u8,
    }
    pub struct EntitySpawnDrop {
        pub varies: u8,  // conditional
    }
    pub struct EntitySpawnTeleport {
        pub unique_id: u32,
        pub region_id: u16,
        pub pos_x: f32,
        pub pos_y: f32,
        pub pos_z: f32,
        pub angle: u16,
        pub portal_state: u8,
        pub quest_flags: u8,
        pub level_restriction: u8,
        pub portal_type: u8,
    }
    pub enum EntitySpawnBody {
        Skillzone(EntitySpawnSkillzone),
        Model(EntitySpawnModel),
        Drop(EntitySpawnDrop),
        Teleport(EntitySpawnTeleport),
    }
    pub struct EntitySpawn {
        pub ref_obj_id: u32,
        pub body: EntitySpawnBody,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpawnBody interface { entitySpawnBody() }
    type EntitySpawnSkillzone struct {
        EntityTypeCode uint16
        SkillID uint32
        UniqueID uint32
        RegionID uint16
        PosX float32
        PosY float32
        PosZ float32
        Angle uint16
    }
    func (*EntitySpawnSkillzone) entitySpawnBody() {}
    type EntitySpawnModel struct {
        Scale uint8
        BerserkLevel uint8
        PVPCapeType uint8
        ExpIconType uint8
        EquipMaxCapacity uint8
        EquipCount uint8
        HP uint32
        RefEventStructID uint32
        State uint16
        UniqueID uint32
        RegionID uint16
        PosX float32
        PosY float32
        PosZ float32
        Angle uint16
        HasMovement bool
        MovementSpeedType uint8
        LifeState uint8
        BodyMode uint8
        MotionState uint8
        GameState uint8
        SpeedWalking float32
        SpeedRunning float32
        SpeedBerserk float32
        BuffCount uint8
        Name string
        JobType uint8
        JobLevel uint8
        PVPState uint8
        IsRiding bool
        InCombat bool
        RidingUniqueID uint32  // conditional
        ScrollingType uint8
        InteractionType uint8
        HwanLevel uint8
        GuildName string
        GuildID uint32
        GuildMemberName string
        GuildLastCrestRev uint32
        UnionID uint32
        UnionLastCrestRev uint32
        IsFriendly bool
        GuildMemberAuthority uint8
        StallTitle string
        StallDecorationID uint32
        HasTalkOptions uint8
    }
    func (*EntitySpawnModel) entitySpawnBody() {}
    type EntitySpawnDrop struct {
        varies uint8  // conditional
    }
    func (*EntitySpawnDrop) entitySpawnBody() {}
    type EntitySpawnTeleport struct {
        UniqueID uint32
        RegionID uint16
        PosX float32
        PosY float32
        PosZ float32
        Angle uint16
        PortalState uint8
        QuestFlags uint8
        LevelRestriction uint8
        PortalType uint8
    }
    func (*EntitySpawnTeleport) entitySpawnBody() {}
    type EntitySpawn struct {
        RefObjID uint32
        Body EntitySpawnBody
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    type EntitySpawnBody =
        | { kind: 'Skillzone'; entityTypeCode: number; skillID: number; uniqueID: number; regionID: number; posX: number; posY: number; posZ: number; angle: number }
        | { kind: 'Model'; scale: number; berserkLevel: number; pVPCapeType: number; expIconType: number; equipMaxCapacity: number; equipCount: number; hP: number; refEventStructID: number; state: number; uniqueID: number; regionID: number; posX: number; posY: number; posZ: number; angle: number; hasMovement: boolean; movementSpeedType: number; lifeState: number; bodyMode: number; motionState: number; gameState: number; speedWalking: number; speedRunning: number; speedBerserk: number; buffCount: number; name: string; jobType: number; jobLevel: number; pVPState: number; isRiding: boolean; inCombat: boolean; ridingUniqueID: number; scrollingType: number; interactionType: number; hwanLevel: number; guildName: string; guildID: number; guildMemberName: string; guildLastCrestRev: number; unionID: number; unionLastCrestRev: number; isFriendly: boolean; guildMemberAuthority: number; stallTitle: string; stallDecorationID: number; hasTalkOptions: number }
        | { kind: 'Drop'; varies: number }
        | { kind: 'Teleport'; uniqueID: number; regionID: number; posX: number; posY: number; posZ: number; angle: number; portalState: number; questFlags: number; levelRestriction: number; portalType: number };
    export interface EntitySpawn {
        refObjID: number;
        body: EntitySpawnBody;
    }
    ```


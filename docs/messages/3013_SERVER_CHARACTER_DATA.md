# SERVER_CHARACTER_DATA

> **Corrected name** (server RE): Was `SERVER_CHARACTER_CREATE_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3013` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6580` |
| Multi-part | Via `0x34A5` begin / `0x34A6` end |

### Fields (Server RE)

The full character data is sent as a multi-part message. This is the largest packet in the protocol.

#### Header

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `ServerTimestamp` | `u32` | 4 | Server time |
| 2 | `RefObjID` | `u32` | 4 | Character model ID |
| 3 | `Scale` | `u8` | 1 | Character scale |
| 4 | `Level` | `u8` | 1 | Current level |
| 5 | `LevelMax` | `u8` | 1 | Maximum level |
| 6 | `Exp` | `u64` | 8 | Current experience |
| 7 | `SPExp` | `u32` | 4 | Skill point experience |
| 8 | `Gold` | `u64` | 8 | Current gold |
| 9 | `SP` | `u32` | 4 | Skill points |
| 10 | `StatPoints` | `u16` | 2 | Available stat points |
| 11 | `BerserkPoints` | `u8` | 1 | Berserk gauge |
| 12 | `GatheredExpPoint` | `u32` | 4 | Gathered exp (guild?) |
| 13 | `HPMax` | `u32` | 4 | Maximum HP |
| 14 | `MPMax` | `u32` | 4 | Maximum MP |
| 15 | `ExpIconType` | `u8` | 1 | SRPlayer.ExpIcon enum |
| 16 | `PKDaily` | `u8` | 1 | Daily PK count |
| 17 | `PKTotal` | `u16` | 2 | Total PK count |
| 18 | `PKPenalty` | `u32` | 4 | PK penalty points |
| 19 | `BerserkLevel` | `u8` | 1 | Berserk mode level |
| 20 | `PVPCapeType` | `u8` | 1 | SRPlayer.PVPCape enum |

#### Inventory

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 21 | `InventoryCapacity` | `u8` | 1 | Max inventory slots |
| 22 | `ItemCount` | `u8` | 1 | Items in inventory |

For each item: `u8 Slot` + [ItemData](../systems/item_structure.md)

#### Avatar Inventory

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 23 | `AvatarCapacity` | `u8` | 1 | Max avatar slots |
| 24 | `AvatarItemCount` | `u8` | 1 | Avatar items equipped |

For each item: `u8 Slot` + [ItemData](../systems/item_structure.md)

#### Masteries

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 25 | `MasterySectionFlag` | `u8` | 1 | Section marker (`0x01`); constant delimiter before mastery loop |

Repeated while `ReadBool() == true`:

| Name | Type | Description |
|------|------|-------------|
| `MasteryID` | `u32` | Mastery reference ID |
| `MasteryLevel` | `u8` | Current mastery level |

#### Skills

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 26 | `SkillSectionFlag` | `u8` | 1 | Section marker (`0x01`); constant delimiter before skill loop |

Repeated while `ReadBool() == true`:

| Name | Type | Description |
|------|------|-------------|
| `SkillID` | `u32` | Skill reference ID |
| `Enabled` | `bool` | Whether skill is active |

#### Completed Quests

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 27 | `CompletedQuestCount` | `u16` | 2 | Number of completed quests |

For each: `u32 QuestID`

#### Active Quests

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 28 | `ActiveQuestCount` | `u8` | 1 | Number of active quests |

For each active quest:

| Name | Type | Description |
|------|------|-------------|
| `QuestID` | `u32` | Quest reference ID |
| `Achievements` | `u8` | Achievement flags |
| `AutoShareRequired` | `bool` | Auto-share flag |
| `QuestType` | `u8` | Quest type ID |
| `TimeRemain` | `u32` | Only if QuestType == 28 |
| `State` | `u8` | Quest state |

If `QuestType != 8`:

| Name | Type | Description |
|------|------|-------------|
| `ObjectiveCount` | `u8` | Number of objectives |

For each objective:

| Name | Type | Description |
|------|------|-------------|
| `ObjectiveID` | `u8` | Objective index |
| `Enabled` | `bool` | Active flag |
| `Name` | `ascii` | Objective name |
| `TaskCount` | `u8` | Number of tasks |
| `TasksID` | `u32[]` | Task reference IDs |

If `QuestType == 88`:

| Name | Type | Description |
|------|------|-------------|
| `NpcCount` | `u8` | Number of quest NPCs |
| `NpcsID` | `u32[]` | NPC reference IDs |

#### Collection Books

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 29 | `CollectionBookEnabled` | `u8` | 1 | Feature flag: `1` if collection books are available, `0` otherwise |
| 30 | `BookCount` | `u32` | 4 | Number of collection books |

For each book:

| Name | Type | Description |
|------|------|-------------|
| `BookID` | `u32` | Book reference ID |
| `StartedDatetime` | `u32` | SRTimeStamp |
| `Pages` | `u32` | Bitmask of collected pages |

#### Position

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 31 | `UniqueID` | `u32` | 4 | Character unique session ID |
| 32 | `RegionID` | `u16` | 2 | Map region |
| 33 | `PosX` | `f32` | 4 | X coordinate |
| 34 | `PosY` | `f32` | 4 | Y coordinate |
| 35 | `PosZ` | `f32` | 4 | Z coordinate |
| 36 | `Angle` | `u16` | 2 | Facing angle |
| 37 | `HasMovement` | `bool` | 1 | Is character moving |
| 38 | `MovementSpeedType` | `u8` | 1 | 0=Walking, 1=Running |

If `HasMovement`:
- If `inDungeon(RegionID)`: `u16 DestRegion, i32 DestX, i32 DestY, i32 DestZ`
- Else: `u16 DestRegion, u16 DestX, u16 DestY, u16 DestZ`

If NOT `HasMovement`:
- `u8 MovementActionType, u16 Angle`

#### States

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 39 | `LifeState` | `u8` | 1 | LIFESTATE_* enum |
| 40 | `BodyMode` | `u8` | 1 | `BODYMODE_*` enum (e.g. 0=Normal, 1=Berserk) — from `BUF_CHARACTER_STATUS` RTTI |
| 41 | `MotionState` | `u8` | 1 | MOTIONSTATE_* enum |
| 42 | `GameState` | `u8` | 1 | BattleState (BATTLESTATE_*) |
| 43 | `SpeedWalking` | `f32` | 4 | Walking speed |
| 44 | `SpeedRunning` | `f32` | 4 | Running speed |
| 45 | `SpeedBerserk` | `f32` | 4 | Berserk speed |

#### Buffs

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 46 | `BuffCount` | `u8` | 1 | Active buff count |

For each buff:

| Name | Type | Description |
|------|------|-------------|
| `SkillID` | `u32` | Buff skill reference ID |
| `BuffUniqueID` | `u32` | Unique instance ID |
| `IsCaster` | `bool` | Only if hasAutoTransferEffect |

#### Identification

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 47 | `Name` | `ascii` | var | Character name |
| 48 | `JobName` | `ascii` | var | Trade job codename |
| 49 | `JobType` | `u8` | 1 | 0=None, 1=Trader, 2=Thief, 3=Hunter |
| 50 | `JobLevel` | `u8` | 1 | Trade job level |
| 51 | `JobExp` | `u32` | 4 | Trade job experience |
| 52 | `JobContribution` | `u32` | 4 | Trade job contribution |
| 53 | `JobReward` | `u32` | 4 | Trade job reward |
| 54 | `PVPState` | `u8` | 1 | PvPSTATE_* enum |
| 55 | `IsRiding` | `bool` | 1 | Is on mount |
| 56 | `InCombat` | `bool` | 1 | BATTLESTATE |
| 57 | `RidingUniqueID` | `u32` | 4 | Only if IsRiding |
| 58 | `CaptureTheFlagType` | `u8` | 1 | CTF event type |
| 59 | `GuideFlag` | `u64` | 8 | Tutorial completion bitmask |
| 60 | `JoinID` | `u32` | 4 | Player session ID (JID) |
| 61 | `IsGameMaster` | `bool` | 1 | GM flag |

Game Settings config data follows (structure varies).

### Structure Summary

```
  // Header
  ServerTimestamp                       u32
  RefObjID                             u32
  Scale                                u8
  Level                                u8
  LevelMax                             u8
  Exp                                  u64
  SPExp                                u32
  Gold                                 u64
  SP                                   u32
  StatPoints                           u16
  BerserkPoints                        u8
  GatheredExpPoint                     u32
  HPMax                                u32
  MPMax                                u32
  ExpIconType                          u8
  PKDaily                              u8
  PKTotal                              u16
  PKPenalty                            u32
  BerserkLevel                         u8
  PVPCapeType                          u8

  // Inventory
  InventoryCapacity                    u8
  ItemCount                            u8
  for each: Slot u8, ItemData

  // Avatar Inventory
  AvatarCapacity                       u8
  AvatarItemCount                      u8
  for each: Slot u8, ItemData

  // Masteries
  MasterySectionFlag                   u8        // constant 0x01
  while ReadBool():
    MasteryID                          u32
    MasteryLevel                       u8

  // Skills
  SkillSectionFlag                     u8        // constant 0x01
  while ReadBool():
    SkillID                            u32
    Enabled                            bool

  // Completed Quests
  CompletedQuestCount                  u16
  for each: QuestID u32

  // Active Quests
  ActiveQuestCount                     u8
  for each: QuestID, Achievements, AutoShareRequired, QuestType, ...

  // Collection Books
  CollectionBookEnabled                u8        // 1=feature active, 0=disabled
  BookCount                            u32
  for each: BookID u32, StartedDatetime u32, Pages u32

  // Position
  UniqueID                             u32
  RegionID                             u16
  PosX/Y/Z                            f32
  Angle                                u16
  HasMovement                          bool
  MovementSpeedType                    u8
  (movement destination or action)

  // States
  LifeState                            u8
  BodyMode                             u8        // BODYMODE_*
  MotionState                          u8
  GameState (BattleState)              u8
  SpeedWalking/Running/Berserk         f32

  // Buffs
  BuffCount                            u8
  for each: SkillID u32, BuffUniqueID u32, [IsCaster bool]

  // Identification
  Name, JobName                        ascii
  JobType, JobLevel                    u8
  JobExp, JobContribution, JobReward   u32
  PVPState                             u8
  IsRiding, InCombat                   bool
  [RidingUniqueID]                     u32
  CaptureTheFlagType                   u8
  GuideFlag                            u64
  JoinID                               u32
  IsGameMaster                         bool
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterData {
        uint32_t ServerTimestamp;
        uint32_t RefObjID;
        uint8_t Scale;
        uint8_t Level;
        uint8_t LevelMax;
        uint64_t Exp;
        uint32_t SPExp;
        uint64_t Gold;
        uint32_t SP;
        uint16_t StatPoints;
        uint8_t BerserkPoints;
        uint32_t GatheredExpPoint;
        uint32_t HPMax;
        uint32_t MPMax;
        uint8_t ExpIconType;
        uint8_t PKDaily;
        uint16_t PKTotal;
        uint32_t PKPenalty;
        uint8_t BerserkLevel;
        uint8_t PVPCapeType;
        uint8_t InventoryCapacity;
        uint8_t ItemCount;
        uint8_t AvatarCapacity;
        uint8_t AvatarItemCount;
        uint8_t MasterySectionFlag;
        uint32_t MasteryID;
        uint8_t MasteryLevel;
        uint8_t SkillSectionFlag;
        uint32_t SkillID;
        bool Enabled;
        uint16_t CompletedQuestCount;
        uint8_t ActiveQuestCount;
        uint32_t QuestID;
        uint8_t Achievements;
        bool AutoShareRequired;
        uint8_t QuestType;
        uint32_t TimeRemain;  // conditional
        uint8_t State;
        uint8_t ObjectiveCount;
        uint8_t ObjectiveID;
        std::string Name;
        uint8_t TaskCount;
        uint8_t TasksID;
        uint8_t NpcCount;
        uint8_t NpcsID;
        uint8_t CollectionBookEnabled;  // conditional
        uint32_t BookCount;
        uint32_t BookID;
        uint32_t StartedDatetime;
        uint32_t Pages;
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
        uint32_t BuffUniqueID;
        bool IsCaster;  // conditional
        std::string JobName;
        uint8_t JobType;
        uint8_t JobLevel;
        uint32_t JobExp;
        uint32_t JobContribution;
        uint32_t JobReward;
        uint8_t PVPState;
        bool IsRiding;
        bool InCombat;
        uint32_t RidingUniqueID;  // conditional
        uint8_t CaptureTheFlagType;
        uint64_t GuideFlag;
        uint32_t JoinID;
        bool IsGameMaster;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterData(
        uint ServerTimestamp,
        uint RefObjID,
        byte Scale,
        byte Level,
        byte LevelMax,
        ulong Exp,
        uint SPExp,
        ulong Gold,
        uint SP,
        ushort StatPoints,
        byte BerserkPoints,
        uint GatheredExpPoint,
        uint HPMax,
        uint MPMax,
        byte ExpIconType,
        byte PKDaily,
        ushort PKTotal,
        uint PKPenalty,
        byte BerserkLevel,
        byte PVPCapeType,
        byte InventoryCapacity,
        byte ItemCount,
        byte AvatarCapacity,
        byte AvatarItemCount,
        byte MasterySectionFlag,
        uint MasteryID,
        byte MasteryLevel,
        byte SkillSectionFlag,
        uint SkillID,
        bool Enabled,
        ushort CompletedQuestCount,
        byte ActiveQuestCount,
        uint QuestID,
        byte Achievements,
        bool AutoShareRequired,
        byte QuestType,
        uint TimeRemain /* conditional */,
        byte State,
        byte ObjectiveCount,
        byte ObjectiveID,
        string Name,
        byte TaskCount,
        byte TasksID,
        byte NpcCount,
        byte NpcsID,
        byte CollectionBookEnabled /* conditional */,
        uint BookCount,
        uint BookID,
        uint StartedDatetime,
        uint Pages,
        uint UniqueID,
        ushort RegionID,
        float PosX,
        float PosY,
        float PosZ,
        ushort Angle,
        bool HasMovement,
        byte MovementSpeedType,
        byte LifeState,
        byte BodyMode,
        byte MotionState,
        byte GameState,
        float SpeedWalking,
        float SpeedRunning,
        float SpeedBerserk,
        byte BuffCount,
        uint BuffUniqueID,
        bool IsCaster /* conditional */,
        string JobName,
        byte JobType,
        byte JobLevel,
        uint JobExp,
        uint JobContribution,
        uint JobReward,
        byte PVPState,
        bool IsRiding,
        bool InCombat,
        uint RidingUniqueID /* conditional */,
        byte CaptureTheFlagType,
        ulong GuideFlag,
        uint JoinID,
        bool IsGameMaster
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterData {
        pub server_timestamp: u32,
        pub ref_obj_id: u32,
        pub scale: u8,
        pub level: u8,
        pub level_max: u8,
        pub exp: u64,
        pub spexp: u32,
        pub gold: u64,
        pub sp: u32,
        pub stat_points: u16,
        pub berserk_points: u8,
        pub gathered_exp_point: u32,
        pub hpmax: u32,
        pub mpmax: u32,
        pub exp_icon_type: u8,
        pub pkdaily: u8,
        pub pktotal: u16,
        pub pkpenalty: u32,
        pub berserk_level: u8,
        pub pvpcape_type: u8,
        pub inventory_capacity: u8,
        pub item_count: u8,
        pub avatar_capacity: u8,
        pub avatar_item_count: u8,
        pub mastery_section_flag: u8,
        pub mastery_id: u32,
        pub mastery_level: u8,
        pub skill_section_flag: u8,
        pub skill_id: u32,
        pub enabled: bool,
        pub completed_quest_count: u16,
        pub active_quest_count: u8,
        pub quest_id: u32,
        pub achievements: u8,
        pub auto_share_required: bool,
        pub quest_type: u8,
        pub time_remain: u32,  // conditional
        pub state: u8,
        pub objective_count: u8,
        pub objective_id: u8,
        pub name: String,
        pub task_count: u8,
        pub tasks_id: u8,
        pub npc_count: u8,
        pub npcs_id: u8,
        pub collection_book_enabled: u8,  // conditional
        pub book_count: u32,
        pub book_id: u32,
        pub started_datetime: u32,
        pub pages: u32,
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
        pub buff_unique_id: u32,
        pub is_caster: bool,  // conditional
        pub job_name: String,
        pub job_type: u8,
        pub job_level: u8,
        pub job_exp: u32,
        pub job_contribution: u32,
        pub job_reward: u32,
        pub pvpstate: u8,
        pub is_riding: bool,
        pub in_combat: bool,
        pub riding_unique_id: u32,  // conditional
        pub capture_the_flag_type: u8,
        pub guide_flag: u64,
        pub join_id: u32,
        pub is_game_master: bool,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterData struct {
        ServerTimestamp uint32
        RefObjID uint32
        Scale uint8
        Level uint8
        LevelMax uint8
        Exp uint64
        SPExp uint32
        Gold uint64
        SP uint32
        StatPoints uint16
        BerserkPoints uint8
        GatheredExpPoint uint32
        HPMax uint32
        MPMax uint32
        ExpIconType uint8
        PKDaily uint8
        PKTotal uint16
        PKPenalty uint32
        BerserkLevel uint8
        PVPCapeType uint8
        InventoryCapacity uint8
        ItemCount uint8
        AvatarCapacity uint8
        AvatarItemCount uint8
        MasterySectionFlag uint8
        MasteryID uint32
        MasteryLevel uint8
        SkillSectionFlag uint8
        SkillID uint32
        Enabled bool
        CompletedQuestCount uint16
        ActiveQuestCount uint8
        QuestID uint32
        Achievements uint8
        AutoShareRequired bool
        QuestType uint8
        TimeRemain uint32  // conditional
        State uint8
        ObjectiveCount uint8
        ObjectiveID uint8
        Name string
        TaskCount uint8
        TasksID uint8
        NpcCount uint8
        NpcsID uint8
        CollectionBookEnabled uint8  // conditional
        BookCount uint32
        BookID uint32
        StartedDatetime uint32
        Pages uint32
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
        BuffUniqueID uint32
        IsCaster bool  // conditional
        JobName string
        JobType uint8
        JobLevel uint8
        JobExp uint32
        JobContribution uint32
        JobReward uint32
        PVPState uint8
        IsRiding bool
        InCombat bool
        RidingUniqueID uint32  // conditional
        CaptureTheFlagType uint8
        GuideFlag uint64
        JoinID uint32
        IsGameMaster bool
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterData {
        serverTimestamp: number;
        refObjID: number;
        scale: number;
        level: number;
        levelMax: number;
        exp: bigint;
        sPExp: number;
        gold: bigint;
        sP: number;
        statPoints: number;
        berserkPoints: number;
        gatheredExpPoint: number;
        hPMax: number;
        mPMax: number;
        expIconType: number;
        pKDaily: number;
        pKTotal: number;
        pKPenalty: number;
        berserkLevel: number;
        pVPCapeType: number;
        inventoryCapacity: number;
        itemCount: number;
        avatarCapacity: number;
        avatarItemCount: number;
        masterySectionFlag: number;
        masteryID: number;
        masteryLevel: number;
        skillSectionFlag: number;
        skillID: number;
        enabled: boolean;
        completedQuestCount: number;
        activeQuestCount: number;
        questID: number;
        achievements: number;
        autoShareRequired: boolean;
        questType: number;
        timeRemain: number;  // conditional
        state: number;
        objectiveCount: number;
        objectiveID: number;
        name: string;
        taskCount: number;
        tasksID: number;
        npcCount: number;
        npcsID: number;
        collectionBookEnabled: number;  // conditional
        bookCount: number;
        bookID: number;
        startedDatetime: number;
        pages: number;
        uniqueID: number;
        regionID: number;
        posX: number;
        posY: number;
        posZ: number;
        angle: number;
        hasMovement: boolean;
        movementSpeedType: number;
        lifeState: number;
        bodyMode: number;
        motionState: number;
        gameState: number;
        speedWalking: number;
        speedRunning: number;
        speedBerserk: number;
        buffCount: number;
        buffUniqueID: number;
        isCaster: boolean;  // conditional
        jobName: string;
        jobType: number;
        jobLevel: number;
        jobExp: number;
        jobContribution: number;
        jobReward: number;
        pVPState: number;
        isRiding: boolean;
        inCombat: boolean;
        ridingUniqueID: number;  // conditional
        captureTheFlagType: number;
        guideFlag: bigint;
        joinID: number;
        isGameMaster: boolean;
    }
    ```


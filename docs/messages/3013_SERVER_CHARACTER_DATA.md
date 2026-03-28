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
| 25 | `unkByte01` | `u8` | 1 | Mastery section flag |

Repeated while `ReadBool() == true`:

| Name | Type | Description |
|------|------|-------------|
| `MasteryID` | `u32` | Mastery reference ID |
| `MasteryLevel` | `u8` | Current mastery level |

#### Skills

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 26 | `unkByte02` | `u8` | 1 | Skill section flag |

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
| 29 | `unkByte03` | `u8` | 1 | Collection book section flag |
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
| 40 | `unkByte04` | `u8` | 1 | BodyMode (BODYMODE_*) |
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
  unkByte01                            u8
  while ReadBool():
    MasteryID                          u32
    MasteryLevel                       u8

  // Skills
  unkByte02                            u8
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
  unkByte03                            u8
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
  unkByte04 (BodyMode)                 u8
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

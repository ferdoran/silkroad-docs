# SERVER_PARTY_DATA

> Source: Server binary reverse engineering. See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3065` |
| Direction | Server → Client |
| Group | Game (Server→Client) |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unkUint01` | `u32` | 4 | PartyID or PartyNumber |
| 2 | `unkUint02` | `u32` | 4 | PartyLeaderJoinID? |
| 3 | `PurposeType` | `u8` | 1 | Party purpose |
| 4 | `SetupFlags` | `u8` | 1 | Party configuration flags |
| 5 | `PlayerCount` | `u8` | 1 | Number of members |

For each member: [PartyMemberData](#partymemberdata-shared-sub-structure)

### PartyMemberData (shared sub-structure)

Used by both SERVER_PARTY_DATA and [SERVER_PARTY_UPDATE](3864_SERVER_PARTY_UPDATE.md).

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unkByte01` | `u8` | 1 | MemberType? (0=normal) |
| 2 | `MemberID` | `u32` | 4 | JoinID |
| 3 | `Name` | `ascii` | var | Character name |
| 4 | `ModelID` | `u32` | 4 | RefObjID |
| 5 | `Level` | `u8` | 1 | Character level |
| 6 | `HPMP` | `u8` | 1 | Packed: HP% in high nibble, MP% in low nibble |
| 7 | `RegionID` | `u16` | 2 | Map region |
| 8 | `PosX` | `u16/i32` | 2/4 | X coordinate (i32 if dungeon, u16 otherwise) |
| 9 | `PosY` | `u16/i32` | 2/4 | Y coordinate |
| 10 | `PosZ` | `u16/i32` | 2/4 | Z coordinate |
| 11 | `unkByte02` | `u8` | 1 | Possibly BodyMode |
| 12 | `unkByte03` | `u8` | 1 | Possibly LifeState |
| 13 | `unkByte04` | `u8` | 1 | Possibly MotionState |
| 14 | `unkByte05` | `u8` | 1 | Possibly GameState/BattleState |
| 15 | `GuildName` | `ascii` | var | Guild name |
| 16 | `unkByte06` | `u8` | 1 | Possibly GuildMemberAuthority |
| 17 | `MasteryPrimaryID` | `u32` | 4 | Primary mastery |
| 18 | `MasterySecondaryID` | `u32` | 4 | Secondary mastery |

### Structure Summary

```
  [   0] unkUint01                      u32       // PartyID
  [   4] unkUint02                      u32       // PartyLeaderJoinID
  [   8] PurposeType                    u8
  [   9] SetupFlags                     u8
  [  10] PlayerCount                    u8
  for each member:
    unkByte01                           u8
    MemberID                            u32
    Name                                ascii
    ModelID                             u32
    Level                               u8
    HPMP                                u8        // packed HP%/MP%
    RegionID                            u16
    if inDungeon: i32 PosX/Y/Z
    else: u16 PosX/Y/Z
    unkByte02                           u8        // BodyMode?
    unkByte03                           u8        // LifeState?
    unkByte04                           u8        // MotionState?
    unkByte05                           u8        // BattleState?
    GuildName                           ascii
    unkByte06                           u8        // GuildAuthority?
    MasteryPrimaryID                    u32
    MasterySecondaryID                  u32
```

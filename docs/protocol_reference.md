# Protocol Reference

Complete reference for Silkroad Online's network protocol.
**288** documented opcodes across 7 categories.

> **WARNING — Client-Derived Names**: The opcode names in this file were generated from `sro_client.exe` binary analysis. Many are **incorrect**. The table below lists confirmed corrections from server binary RE (`SR_GameServer_Andreas.exe`) cross-referenced with server RE. See [server_binary_analysis.md](../../docs/server_binary_analysis.md) for authoritative packet structures and field names.

## Server-Corrected Opcode Names

| Opcode | Client Name (wrong) | Server Name (correct) | Notes |
|--------|---------------------|----------------------|-------|
| `0x3013` | SERVER_CHARACTER_CREATE_RESPONSE | **SERVER_CHARACTER_DATA** | Full character data (via 0x34A5 begin / 0x34A6 end) |
| `0x3015` | SERVER_CHARACTER_DELETE_RESPONSE | **SERVER_ENTITY_SPAWN** | Entity spawn with type-branching (player/NPC/mob/COS/drop/teleport) |
| `0x3016` | SERVER_CHARACTER_RESTORE | **SERVER_ENTITY_DESPAWN** | Entity removed from world |
| `0x3017` | SERVER_CHARACTER_NAME_CHECK | **SERVER_ENTITY_GROUPSPAWN_BEGIN** | Marks start of group spawn batch |
| `0x3018` | SERVER_CHARACTER_SELECT_RESPONSE | **SERVER_ENTITY_GROUPSPAWN_END** | Marks end of group spawn batch |
| `0x3019` | SERVER_CHARACTER_LOBBY_INFO | **SERVER_ENTITY_GROUPSPAWN_DATA** | Entity data within group spawn |
| `0x3020` | SERVER_CHARACTER_DATA | **SERVER_ENVIROMENT_CELESTIAL_POSITION** | Sun/moon position |
| `0x3026` | SERVER_WEATHER | **SERVER_CHAT_UPDATE** | Chat message broadcast (10 code refs) |
| `0x303D` | SERVER_ENTITY_SPAWN | **SERVER_CHARACTER_STATS_UPDATE** | PhyAtk/MagAtk/Def/Hit/Parry/HP/MP/STR/INT |
| `0x3040` | SERVER_ENTITY_GROUPSPAWN_START | **SERVER_INVENTORY_ITEM_UPDATE** | Item slot changed |
| `0x3042` | SERVER_ENTITY_DESPAWN | **SERVER_STORAGE_DATA_BEGIN** | Storage transfer start |
| `0x3047` | SERVER_ENTITY_UPDATE_POSITION | **SERVER_STORAGE_DATA_BEGIN** | Storage header |
| `0x304E` | SERVER_ENTITY_UPDATE_STATE | **SERVER_CHARACTER_INFO_UPDATE** | Gold/SP/BerserkPoints update |
| `0x3052` | SERVER_ENTITY_MOVEMENT | **SERVER_INVENTORY_ITEM_DURABILITY_UPDATE** | Durability change |
| `0x3054` | SERVER_CHAT_MESSAGE | **SERVER_ENTITY_LEVEL_UP** | Level up notification |
| `0x3056` | SERVER_ENTITY_UPDATE_MOVEMENT | **SERVER_CHARACTER_EXPERIENCE_UPDATE** | Exp received (can be negative) |
| `0x3057` | SERVER_ENTITY_ACTION | **SERVER_ENTITY_STATUS_UPDATE** | HP/MP/BadStatus update with type switch |
| `0x3065` | — | **SERVER_PARTY_DATA** | Party info + member list |
| `0x3091` | SERVER_PARTY_INVITE | **SERVER_ENTITY_EMOTE_USE** | Emote animation |
| `0x3092` | SERVER_PARTY_INFO | **SERVER_INVENTORY_CAPACITY_UPDATE** | Inventory size changed |
| `0x3101` | SERVER_NOTICE_CLEAR | **SERVER_GUILD_DATA** | Guild info (via 0x34B3 begin / 0x34B4 end) |
| `0x30BF` | SERVER_NPC_RESPONSE | **SERVER_ENTITY_STATE_UPDATE** | LifeState/MotionState/BattleState/PVPState |
| `0x30C8` | SERVER_EXCHANGE_START | **SERVER_PET_DATA** | COS data (horse/transport/attack/pick pet) |
| `0x30C9` | SERVER_EXCHANGE_CONFIRM | **SERVER_PET_UPDATE** | COS update (unsummon/exp/hungry/model) |
| `0x30D0` | SERVER_PET_RESPONSE | **SERVER_ENTITY_SPEED_UPDATE** | Walk/Run speed floats |
| `0x34A5` | SERVER_EVENT_RESPONSE | **SERVER_CHARACTER_DATA_BEGIN** | Multi-part character data start |
| `0x34A6` | SERVER_EVENT_ITEM | **SERVER_CHARACTER_DATA_END** | Multi-part character data end |
| `0x34B3` | SERVER_EVENT_UPDATE | **SERVER_GUILD_DATA_BEGIN** | Multi-part guild data start |
| `0x34B4` | SERVER_EVENT_DATA | **SERVER_GUILD_DATA_END** | Multi-part guild data end |
| `0x34B5` | SERVER_EVENT_REWARD | **SERVER_TELEPORT_READY_REQUEST** | Server asks client to prepare teleport |
| `0x3809` | SERVER_TIME_UPDATE | **SERVER_ENVIROMENT_WEATHER_UPDATE** | Weather change |
| `0x3864` | SERVER_WORLD_UPDATE | **SERVER_PARTY_UPDATE** | Party member join/leave/update (31 code refs) |
| `0x38F5` | — | **SERVER_GUILD_UPDATE** | Guild changes (most complex: 31 code refs) |
| `0xB021` | CLIENT_CHARACTER_CREATE | **SERVER_ENTITY_MOVEMENT** | Entity movement broadcast |
| `0xB024` | CLIENT_CHARACTER_LIST_REQUEST | **SERVER_ENTITY_MOVEMENT_ANGLE** | Facing angle update |
| `0xB025` | CLIENT_CHARACTER_DELETE | **SERVER_CHAT_RESPONSE** | Chat message response |
| `0xB034` | CLIENT_ENTITY_SELECT | **SERVER_INVENTORY_ITEM_MOVEMENT** | Item moved in inventory |
| `0xB045` | CLIENT_NPC_INTERACT | **SERVER_ENTITY_SELECTION** | Target selection response |
| `0xB046` | CLIENT_NPC_RESPONSE | **SERVER_ENTITY_TALK_RESPONSE** | NPC dialog response |
| `0xB04C` | CLIENT_GAME_READY | **SERVER_INVENTORY_ITEM_USE** | Item use result |
| `0xB050` | CLIENT_CHAT_REQUEST | **SERVER_CHARACTER_ADD_STR_RESPONSE** | STR point allocation |
| `0xB051` | CLIENT_CHAT_CLEAR | **SERVER_CHARACTER_ADD_INT_RESPONSE** | INT point allocation |
| `0xB059` | CLIENT_EMOTE | **SERVER_TELEPORT_RECALL_RESPONSE** | Recall teleport result |
| `0xB05A` | CLIENT_SIT_STAND | **SERVER_TELEPORT_USE_RESPONSE** | Teleport use result |
| `0xB060` | CLIENT_SIEGE_ACTION | **SERVER_PARTY_INVITATION_RESPONSE** | Party invite result |
| `0xB070` | CLIENT_ENTITY_POSITION_REQUEST | **SERVER_ENTITY_SKILL_START** | Skill cast begin + damage data |
| `0xB071` | CLIENT_ENTITY_DETAIL_REQUEST | **SERVER_ENTITY_SKILL_END** | Skill cast end + damage data |
| `0xB072` | CLIENT_ENTITY_STATUS_REQUEST | **SERVER_ENTITY_SKILL_BUFF_REMOVED** | Buff removed |
| `0xB0A1` | CLIENT_SKILL_REQUEST | **SERVER_MASTERY_SKILL_LEVELUP_RESPONSE** | Skill level up result |
| `0xB0A2` | CLIENT_SKILL_USE | **SERVER_MASTERY_LEVELUP_RESPONSE** | Mastery level up result |
| `0xB0B1` | — | **SERVER_STALL_CREATE_RESPONSE** | Player shop creation |
| `0xB0BD` | CLIENT_STORAGE_REQUEST | **SERVER_ENTITY_SKILL_BUFF_ADDED** | New buff applied |
| `0xB0CB` | CLIENT_QUEST_REQUEST | **SERVER_PET_PLAYER_MOUNTED** | Mount/dismount |

## Server-Identified "unk" Field Names

Fields previously marked as "unk" have been identified from server debug strings:

| Packet | Original Field | Server Name | Values |
|--------|-----------|-------------|--------|
| 0x3013/0x3015 States | `unkByte04` | **BodyMode** | NORMAL=0, HWAN=1, BERSERKER=2, INVINCIBLE=3, INVISIBLE=4 |
| 0x3013/0x3015 States | `GameState` | **BattleState** | IN_PEACE=0, IN_BATTLE=1 |
| 0x3015 Player | `unkByte03` | **HwanLevel** | From `UpdateHwanLevel()` |
| 0x3057 Status | `unkByte01/02` | **StatusTargetType, StatusSourceType** | Damage source/target flags |
| 0xB070 Skill | `unkByte01` | **SkillExecutionMode** | Skill execution flag |
| 0x3065 Party | `unkByte02-05` | **BodyMode, LifeState, MotionState, BattleState** | Same state fields as entity spawn |
| 0x3065 Party | `unkByte06` | **GuildMemberAuthority** | Permission level |
| 0x3101 Guild | `unkUInt00` | **UnionID/AllianceID** | Alliance reference |
| 0x3101 Guild | `unkByte00` | **GuildStorageSlots** | Storage capacity |
| 0x3101 GuildMember | `unkUInt01` | **LastLoginTime** | Timestamp |
| 0x3101 GuildMember | `unkUInt02` | **DonateGP** | Guild point donations |
| 0x3101 GuildMember | `unkUInt03` | **CharDBID** | Character database ID |

## Message Index

The complete opcode listing with field counts, directions, and links to per-message pages is in the [Message Index](messages/INDEX.md).

## Variable-Length Messages

181 messages have variable-length structures where fields depend on earlier values.


### Common Patterns


**Result-based branching** (most common): The first byte is a result code.
- `result == 1`: Success — additional data fields follow
- `result == 2`: Failure — error code may follow, fewer fields

**Type-based branching**: A type byte determines which set of fields follows.
Used in entity updates, skill handlers, COS commands.

**Count-based loops**: A count field precedes a repeated structure.
Used in party member lists, guild member lists, inventory operations.


## Statistics

| Metric | Count |
|--------|-------|
| Total opcodes | 288 |
| Total fields documented | 1816 |
| Variable-length messages | 181 |
| Messages with string references | 105 |
| Decompiled handlers | 295 |

---

## Request ↔ Response Opcode Mapping

The client sends **request** messages using opcodes in the `0x70xx` range. The server responds with the corresponding `0xB0xx` opcode (offset `+0x4000`). For example, a request with opcode `0x7034` gets a response on `0xB034`.

**Mapping formula**: Response opcode = Request opcode + 0x4000

| Request | Response | Name | Request Fields |
|---------|----------|------|----------------|
| `0x7001` | `0xB001` | Authentication | `u16`, `?` |
| `0x7005` | `0xB005` | Login | *(via CSession)* |
| `0x7006` | `0xB006` | Auth Challenge | *(via CSession)* |
| `0x7010` | `0xB010` | Character Select | `u16` (character index) |
| `0x7021` | `0xB021` | Character Create | *(complex)* |
| `0x7023` | `0xB023` | Character Delete Confirm | *(via CSession)* |
| `0x7024` | `0xB024` | Character List | *(via CSession)* |
| `0x7025` | `0xB025` | Character Delete | *(via CSession)* |
| `0x7031` | `0xB031` | Movement Cancel | `u32` (posX), `u32` (posZ), `u8` (type) |
| `0x7034` | `0xB034` | Entity Select | *(via CSession)* |
| `0x703C` | `0xB03C` | Entity Action | *(via CSession)* |
| `0x703E` | `0xB03E` | Entity Interact | `u32` (uniqueID), `u8` (flags) |
| `0x703F` | `0xB03F` | Entity Deselect | `u32` (uniqueID), `u8` (action) |
| `0x7045` | `0xB045` | NPC Interact | *(via CSession)* |
| `0x7046` | `0xB046` | NPC Response | `?`, `?`, `u8` (option) |
| `0x704B` | `0xB04B` | Game Option | *(via CSession)* |
| `0x704C` | `0xB04C` | Game Ready | `u8` (flag), `u16` (param) |
| `0x704F` | `0xB04F` | Unique ID Request | *(via CSession)* |
| `0x7050` | `0xB050` | Chat | *(via CSession)* |
| `0x7051` | `0xB051` | Chat Clear | *(via CSession)* |
| `0x7059` | `0xB059` | Emote | *(via CSession)* |
| `0x705A` | `0xB05A` | Sit/Stand | *(via CSession)* |
| `0x705B` | `0xB05B` | Update State | *(via CSession)* |
| `0x705D` | `0xB05D` | Siege Request | `u32` (fortressID) |
| `0x705E` | `0xB05E` | Siege Response | `u32`, `?`, `u32` |
| `0x7060` | `0xB060` | Siege Action | `u32` (targetID), `u8` (action) |
| `0x7062` | `0xB062` | Party Create | `u32` (settings) |
| `0x7063` | `0xB063` | Party Settings | `u32` (settings) |
| `0x7069` | `0xB069` | Join Party | *(via CSession)* |
| `0x706A` | `0xB06A` | Leave Party | *(via CSession)* |
| `0x706B` | `0xB06B` | Kick Party Member | `u32` (memberUID) |
| `0x706C` | `0xB06C` | Party Response | *(via CSession)* |
| `0x706D` | `0xB06D` | Party Match Request | `u32` (partyID) |
| `0x7074` | `0xB074` | Entity Info | `u8` (type) |
| `0x7081` | `0xB081` | Inventory Operation | *(via CSession)* |
| `0x7082` | `0xB082` | Inventory Move | *(via CSession)* |
| `0x7083` | `0xB083` | Inventory Use | *(via CSession)* |
| `0x7084` | `0xB084` | Inventory Drop | *(via CSession)* |
| `0x70A1` | `0xB0A1` | Skill Use | `u32` (skillID) |
| `0x70A2` | `0xB0A2` | Skill Learn | `u32` (skillID), `u8` (action) |
| `0x70A7` | `0xB0A7` | Party Request | *(via CSession)* |
| `0x70B1` | `0xB0B1` | Party Invite | `u16`, `?` |
| `0x70B3` | `0xB0B3` | Stall Create | `u32` (stallID) |
| `0x70BA` | `0xB0BA` | Guild Request | `u8`, `u8`, `u16`, `u64`, `u16`, `u8`, `u8`, `u16`, `u64`, `u8`, `u16`, `u8`, `u16`, `u8` |
| `0x70C0` | `0xB0C0` | Pet Command | *(via CSession)* |
| `0x70C5` | `0xB0C5` | Pet Action | *(via CSession)* |
| `0x70C6` | `0xB0C6` | NPC Data Request | `u32` (npcUID) |
| `0x70C7` | `0xB0C7` | NPC Close | `u32` (npcUID), `u8` (action) |
| `0x70CB` | `0xB0CB` | Quest Action | `?`, `u32` (questID) |
| `0x70D8` | `0xB0D8` | Stall Open | `u32` (stallID) |
| `0x70D9` | `0xB0D9` | Stall Modify | `u32` (stallID) |
| `0x70DB` | `0xB0DB` | Alchemy Start | *(via CSession)* |
| `0x70E1` | `0xB0E1` | Exchange Request | `u32` (targetUID), `u8` (jobType) |
| `0x70E2` | `0xB0E2` | Exchange Confirm | `u32` (exchangeID) |
| `0x70E3` | `0xB0E3` | Exchange Approve | `u32` (exchangeID), `u8` (approve) |
| `0x70E4` | `0xB0E4` | Title Set | `u32` (titleID), `u8` (action), `u8` (slot) |
| `0x70E5` | `0xB0E5` | Equipment Update | `u32` (itemUID), `u8` (slot) |
| `0x70E6` | `0xB0E6` | Item Action | `u32` (itemUID) |
| `0x70EA` | `0xB0EA` | Gold Pickup | `u64` (goldAmount) |
| `0x70F1` | `0xB0F1` | Guild Data Request | `u32` (guildID) |
| `0x70F2` | `0xB0F2` | Guild Update Request | `u32` (guildID) |
| `0x70F3` | `0xB0F3` | Guild Full Data | `u32` (guildID) |
| `0x70F6` | `0xB0F6` | SP Update | `u32` (param1), `u32` (param2) |
| `0x70FA` | `0xB0FA` | XP Request | `u32` (param) |
| `0x70FB` | `0xB0FB` | Guild Status | `u32` (guildID) |
| `0x70FD` | `0xB0FD` | PVP Request | `u32` (param) |
| `0x70FF` | `0xB0FF` | Berserk Request | `u32` (param), `u8` (action) |
| `0x7103` | `0xB103` | Job Request | `u32` (param1), `u32` (param2) |
| `0x7105` | `0xB105` | Job Data | `u32` (jobID) |
| `0x7106` | `0xB106` | Job Update | `u32` (param) |
| `0x7107` | `0xB107` | Job Detail | `u32` (param1), `u32` (param2), `u8` (type) |
| `0x7110` | `0xB110` | COS Request | `u8` (type), `u32` (cosUID), `u8` (subType), `u32` (targetGuildID) |
| `0x7112` | `0xB112` | COS Action | `u32` (cosUID) |
| `0x7113` | `0xB113` | COS Data | `u32` (cosUID) |
| `0x7114` | `0xB114` | COS Update | `u32` (cosUID) |
| `0x7116` | `0xB116` | COS Info | `u32` (cosUID) |
| `0x7117` | `0xB117` | COS GID | `u32` (cos_gid) |
| `0x7121` | `0xB121` | Arena Request | `u16` (arenaID) |
| `0x715F` | `0xB15F` | COS Remove | `u32` (cosUID), `u32` (param), `u8` (action), `u32` (extra) |
| `0x7160` | `0xB160` | Arena Action | `u32` (arenaID), `u32` (param) |
| `0x7168` | `0xB168` | Arena Data | `u32` (arenaID), `u8` (type) |
| `0x7202` | `0xB202` | Skill Data | `u32` (masteryID), `u32` (skillID), `u8` (action) |
| `0x7203` | `0xB203` | Skill Update | `u32` (masteryID), `u32` (skillID), `u8` (action) |
| `0x7250` | `0xB250` | Academy Update | `u32` (param) |
| `0x7251` | `0xB251` | Academy Detail | `u32` (param) |
| `0x7252` | `0xB252` | Academy Action | `u32` (param) |
| `0x7256` | `0xB256` | Arena Update | `u32` (param), `u16` (itemID), `?` |
| `0x7258` | `0xB258` | Arena Detail | `u32` (param) |
| `0x7259` | `0xB259` | Arena Info | `u32` (param), `u8` (type) |
| `0x7304` | `0xB304` | Party Member | `u32` (memberUID) |
| `0x730B` | `0xB30B` | Guild Data | `u32` (guildID), `u32` (memberUID), `u8` (action) |
| `0x730C` | `0xB30C` | Guild Info | `u8`, `u8`, `u16`, `?`, `u16`, `?` |
| `0x7420` | `0xB420` | Event NPC | `u32` (npcUID), `u8` (action), `u32` (param) |
| `0x7461` | `0xB461` | Fortress Action | `u8` (type), `u8` (action), `u32` (fortressID), `u8` (flag) |
| `0x7463` | `0xB463` | Fortress Data | `u32` (fortressID), `u8` (type), `u64` (data), `u16` (param), `u8` (flag), `u64` (extra) |
| `0x7470` | `0xB470` | Stall Browse | `u32` (stallUID) |
| `0x7472` | `0xB472` | Stall Action | `u32` (stallUID) |
| `0x7478` | `0xB478` | Stall Confirm | `u32` (stallUID) |
| `0x747C` | `0xB47C` | Ranking Action | `u32` (rankingID) |
| `0x747E` | `0xB47E` | Guild Data 2 | `u32` (guildID) |
| `0x74D4` | `0xB4D4` | Fortress Update | `u32` (fortressID) |
| `0x7501` | `0xB501` | COS Status | `u32` (cosUID) |
| `0x7506` | `0xB506` | Ranking Detail | `u8` (type), `u32` (rankingID), `u32` (page) |
| `0x750B` | `0xB50B` | Ranking Full | `u32` (rankingID) |
| `0x750C` | `0xB50C` | Ranking Score | `u8`, `u8`, `u32` (playerUID), `u8` (type), `u16` (param), `?` |
| `0x7515` | `0xB515` | Battle Siege | `u32` (fortressID), `u8` (action) |
| `0x7519` | `0xB519` | Battle Data | `u32` (battleID) |
| `0x751A` | `0xB51A` | Battle Update | `u32` (battleID) |
| `0x751C` | `0xB51C` | Battle Info | `u32` (param1), `u32` (param2), `u8` (type) |
| `0x751D` | `0xB51D` | Battle Detail | `u32` (battleID) |

### Message Building Pattern

The client builds outgoing messages using `CMsgStreamBuffer`:

```
1. CMsgStreamBuffer::Init(opcode)     - Initialize with opcode at [msg+0x18]
2. CMsgStreamBuffer::Write(src, size) - Write field data (repeated per field)
3. CSession::Send(msg)               - Send the built message
4. CMsgStreamBuffer::Destroy()        - Cleanup
```

Key functions:

| Address | Function | Purpose |
|---------|----------|---------|
| `0x0053CEA0` | `CMsgStreamBuffer::Init` | Set opcode, allocate buffer |
| `0x00508FE0` | `CMsgStreamBuffer::Write` | Write N bytes to stream |
| `0x008418D0` | `CSession::Send` | Send message via network |
| `0x005097A0` | `CMsgStreamBuffer::Destroy` | Free buffer |
| `0x00841780` | `CSession::AcquireLock` | Lock for thread safety |
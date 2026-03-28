# Protocol Reference

Complete reference for Silkroad Online's network protocol.
**288** documented opcodes across 7 categories.

> **WARNING — Client-Derived Names**: The opcode names in this file were generated from `sro_client.exe` binary analysis. Many are **incorrect**. The table below lists confirmed corrections from server binary RE (`SR_GameServer_Andreas.exe`) cross-referenced with xBot source. See [server_binary_analysis.md](../../docs/server_binary_analysis.md) for authoritative packet structures and field names.

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

Fields marked as "unk" in xBot source have been identified from server debug strings:

| Packet | xBot Field | Server Name | Values |
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

## Message Categories


### Security/Handshake (2 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0x0FFC` | [SYSTEM_KEEPALIVE](messages/0FFC_SYSTEM_KEEPALIVE.md) | 5 |  |  |
| `0x0FFD` | [SYSTEM_PING](messages/0FFD_SYSTEM_PING.md) | 0 |  |  |

### Server → Client (Game World) (134 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0x2000` | [LOGIN_AUTH](messages/2000_LOGIN_AUTH.md) | 0 |  |  |
| `0x300A` | [SERVER_LOGIN_RESPONSE](messages/300A_SERVER_LOGIN_RESPONSE.md) | 2 | Yes |  |
| `0x300C` | [SERVER_PATCH_INFO](messages/300C_SERVER_PATCH_INFO.md) | 3 |  |  |
| `0x3011` | [SERVER_CHARACTER_LIST](messages/3011_SERVER_CHARACTER_LIST.md) | 2 |  |  |
| `0x3013` | [SERVER_CHARACTER_CREATE_RESPONSE](messages/3013_SERVER_CHARACTER_CREATE_RESPONSE.md) | 0 |  |  |
| `0x3015` | [SERVER_CHARACTER_DELETE_RESPONSE](messages/3015_SERVER_CHARACTER_DELETE_RESPONSE.md) | 0 | Yes |  |
| `0x3016` | [SERVER_CHARACTER_RESTORE](messages/3016_SERVER_CHARACTER_RESTORE.md) | 4 |  |  |
| `0x3017` | [SERVER_CHARACTER_NAME_CHECK](messages/3017_SERVER_CHARACTER_NAME_CHECK.md) | 4 |  |  |
| `0x3018` | [SERVER_CHARACTER_SELECT_RESPONSE](messages/3018_SERVER_CHARACTER_SELECT_RESPONSE.md) | 0 | Yes |  |
| `0x3019` | [SERVER_CHARACTER_LOBBY_INFO](messages/3019_SERVER_CHARACTER_LOBBY_INFO.md) | 2 |  |  |
| `0x3020` | [SERVER_CHARACTER_DATA](messages/3020_SERVER_CHARACTER_DATA.md) | 0 | Yes |  |
| `0x3026` | [SERVER_WEATHER](messages/3026_SERVER_WEATHER.md) | 6 | Yes |  |
| `0x3028` | [SERVER_UNIQUE_ID](messages/3028_SERVER_UNIQUE_ID.md) | 3 |  |  |
| `0x302D` | [SERVER_ENTITY_SPEED](messages/302D_SERVER_ENTITY_SPEED.md) | 2 |  |  |
| `0x3036` | [SERVER_ENTITY_HP_MP](messages/3036_SERVER_ENTITY_HP_MP.md) | 3 |  |  |
| `0x303D` | [SERVER_ENTITY_SPAWN](messages/303D_SERVER_ENTITY_SPAWN.md) | 26 | Yes |  |
| `0x3040` | [SERVER_ENTITY_GROUPSPAWN_START](messages/3040_SERVER_ENTITY_GROUPSPAWN_START.md) | 7 | Yes |  |
| `0x3041` | [SERVER_ENTITY_GROUPSPAWN_END](messages/3041_SERVER_ENTITY_GROUPSPAWN_END.md) | 1 |  |  |
| `0x3042` | [SERVER_ENTITY_DESPAWN](messages/3042_SERVER_ENTITY_DESPAWN.md) | 4 | Yes |  |
| `0x3047` | [SERVER_ENTITY_UPDATE_POSITION](messages/3047_SERVER_ENTITY_UPDATE_POSITION.md) | 6 |  |  |
| `0x3048` | [SERVER_ENTITY_ITEM_SPAWN](messages/3048_SERVER_ENTITY_ITEM_SPAWN.md) | 40 | Yes |  |
| `0x3049` | [SERVER_ENTITY_PICKUP](messages/3049_SERVER_ENTITY_PICKUP.md) | 1 |  |  |
| `0x304D` | [SERVER_ENTITY_UPDATE_STATUS](messages/304D_SERVER_ENTITY_UPDATE_STATUS.md) | 2 | Yes |  |
| `0x304E` | [SERVER_ENTITY_UPDATE_STATE](messages/304E_SERVER_ENTITY_UPDATE_STATE.md) | 8 | Yes |  |
| `0x3052` | [SERVER_ENTITY_MOVEMENT](messages/3052_SERVER_ENTITY_MOVEMENT.md) | 9 | Yes | skill |
| `0x3054` | [SERVER_CHAT_MESSAGE](messages/3054_SERVER_CHAT_MESSAGE.md) | 5 | Yes |  |
| `0x3055` | [SERVER_CHAT_UPDATE](messages/3055_SERVER_CHAT_UPDATE.md) | 0 |  |  |
| `0x3056` | [SERVER_ENTITY_UPDATE_MOVEMENT](messages/3056_SERVER_ENTITY_UPDATE_MOVEMENT.md) | 1 |  |  |
| `0x3057` | [SERVER_ENTITY_ACTION](messages/3057_SERVER_ENTITY_ACTION.md) | 2 |  |  |
| `0x3058` | [SERVER_ENTITY_BUFF](messages/3058_SERVER_ENTITY_BUFF.md) | 3 |  |  |
| `0x305C` | [SERVER_ENTITY_NAME](messages/305C_SERVER_ENTITY_NAME.md) | 5 | Yes |  |
| `0x3068` | [SERVER_ENTITY_DAMAGE](messages/3068_SERVER_ENTITY_DAMAGE.md) | 4 | Yes |  |
| `0x3076` | [SERVER_ENTITY_UPDATE_EXP](messages/3076_SERVER_ENTITY_UPDATE_EXP.md) | 7 |  |  |
| `0x3077` | [SERVER_ENTITY_LEVEL_UP](messages/3077_SERVER_ENTITY_LEVEL_UP.md) | 2 | Yes |  |
| `0x3078` | [SERVER_ENTITY_STATS](messages/3078_SERVER_ENTITY_STATS.md) | 34 | Yes |  |
| `0x3086` | [SERVER_INVENTORY_ITEM](messages/3086_SERVER_INVENTORY_ITEM.md) | 38 | Yes |  |
| `0x3087` | [SERVER_INVENTORY_OPEN](messages/3087_SERVER_INVENTORY_OPEN.md) | 0 |  |  |
| `0x3088` | [SERVER_INVENTORY_CLOSE](messages/3088_SERVER_INVENTORY_CLOSE.md) | 0 |  |  |
| `0x3089` | [SERVER_INVENTORY_OPERATION](messages/3089_SERVER_INVENTORY_OPERATION.md) | 1 | Yes |  |
| `0x3091` | [SERVER_PARTY_INVITE](messages/3091_SERVER_PARTY_INVITE.md) | 4 | Yes |  |
| `0x3092` | [SERVER_PARTY_INFO](messages/3092_SERVER_PARTY_INFO.md) | 4 | Yes |  |
| `0x30A6` | [SERVER_GUILD_INFO](messages/30A6_SERVER_GUILD_INFO.md) | 2 | Yes |  |
| `0x30B7` | [SERVER_TELEPORT_START](messages/30B7_SERVER_TELEPORT_START.md) | 2 |  |  |
| `0x30B8` | [SERVER_TELEPORT_READY](messages/30B8_SERVER_TELEPORT_READY.md) | 1 | Yes |  |
| `0x30B9` | [SERVER_TELEPORT_DATA](messages/30B9_SERVER_TELEPORT_DATA.md) | 4 | Yes |  |
| `0x30BF` | [SERVER_NPC_RESPONSE](messages/30BF_SERVER_NPC_RESPONSE.md) | 13 |  |  |
| `0x30C2` | [SERVER_SKILL_RESPONSE](messages/30C2_SERVER_SKILL_RESPONSE.md) | 1 |  |  |
| `0x30C3` | [SERVER_SKILL_DATA](messages/30C3_SERVER_SKILL_DATA.md) | 0 | Yes |  |
| `0x30C8` | [SERVER_EXCHANGE_START](messages/30C8_SERVER_EXCHANGE_START.md) | 5 |  |  |
| `0x30C9` | [SERVER_EXCHANGE_CONFIRM](messages/30C9_SERVER_EXCHANGE_CONFIRM.md) | 2 | Yes |  |
| `0x30CA` | [SERVER_EXCHANGE_APPROVE](messages/30CA_SERVER_EXCHANGE_APPROVE.md) | 2 | Yes |  |
| `0x30CD` | [SERVER_STORAGE_RESPONSE](messages/30CD_SERVER_STORAGE_RESPONSE.md) | 2 |  |  |
| `0x30CE` | [SERVER_STORAGE_DATA](messages/30CE_SERVER_STORAGE_DATA.md) | 1 |  |  |
| `0x30D0` | [SERVER_PET_RESPONSE](messages/30D0_SERVER_PET_RESPONSE.md) | 2 | Yes |  |
| `0x30D1` | [SERVER_PET_DATA](messages/30D1_SERVER_PET_DATA.md) | 3 |  |  |
| `0x30D3` | [SERVER_PET_STATUS](messages/30D3_SERVER_PET_STATUS.md) | 1 |  |  |
| `0x30D4` | [SERVER_PET_UPDATE](messages/30D4_SERVER_PET_UPDATE.md) | 4 | Yes |  |
| `0x30D5` | [SERVER_PET_EXPERIENCE](messages/30D5_SERVER_PET_EXPERIENCE.md) | 1 |  |  |
| `0x30D6` | [SERVER_QUEST_DATA](messages/30D6_SERVER_QUEST_DATA.md) | 10 | Yes |  |
| `0x30D7` | [SERVER_QUEST_UPDATE](messages/30D7_SERVER_QUEST_UPDATE.md) | 6 | Yes |  |
| `0x30DA` | [SERVER_STALL_RESPONSE](messages/30DA_SERVER_STALL_RESPONSE.md) | 3 | Yes |  |
| `0x30DC` | [SERVER_STALL_DATA](messages/30DC_SERVER_STALL_DATA.md) | 2 |  |  |
| `0x30DF` | [SERVER_ALCHEMY_RESPONSE](messages/30DF_SERVER_ALCHEMY_RESPONSE.md) | 2 |  |  |
| `0x30E0` | [SERVER_ALCHEMY_DATA](messages/30E0_SERVER_ALCHEMY_DATA.md) | 2 |  |  |
| `0x30E6` | [SERVER_TITLE_DATA](messages/30E6_SERVER_TITLE_DATA.md) | 3 |  |  |
| `0x30E7` | [SERVER_ENTITY_UPDATE_EQUIPMENT](messages/30E7_SERVER_ENTITY_UPDATE_EQUIPMENT.md) | 44 | Yes |  |
| `0x30E8` | [SERVER_ITEM_UPDATE](messages/30E8_SERVER_ITEM_UPDATE.md) | 2 | Yes |  |
| `0x30EB` | [SERVER_ENTITY_BERSERK](messages/30EB_SERVER_ENTITY_BERSERK.md) | 3 | Yes |  |
| `0x30EC` | [SERVER_ENTITY_UPDATE_GOLD](messages/30EC_SERVER_ENTITY_UPDATE_GOLD.md) | 2 | Yes | quest |
| `0x30EF` | [SERVER_SIEGE_DATA](messages/30EF_SERVER_SIEGE_DATA.md) | 8 | Yes |  |
| `0x30FF` | [SERVER_ENTITY_UPDATE_SP](messages/30FF_SERVER_ENTITY_UPDATE_SP.md) | 2 | Yes |  |
| `0x3100` | [SERVER_NOTICE](messages/3100_SERVER_NOTICE.md) | 9 | Yes |  |
| `0x3101` | [SERVER_NOTICE_CLEAR](messages/3101_SERVER_NOTICE_CLEAR.md) | 0 | Yes |  |
| `0x3102` | [SERVER_ENTITY_RESURRECT](messages/3102_SERVER_ENTITY_RESURRECT.md) | 2 | Yes |  |
| `0x3103` | [SERVER_GLOBAL_CHAT](messages/3103_SERVER_GLOBAL_CHAT.md) | 5 | Yes |  |
| `0x3109` | [SERVER_ENTITY_UPDATE_XP](messages/3109_SERVER_ENTITY_UPDATE_XP.md) | 2 | Yes |  |
| `0x3120` | [SERVER_ENTITY_UPDATE_GUILD](messages/3120_SERVER_ENTITY_UPDATE_GUILD.md) | 2 |  |  |
| `0x3122` | [SERVER_ENTITY_UPDATE_PVP](messages/3122_SERVER_ENTITY_UPDATE_PVP.md) | 2 |  |  |
| `0x3153` | [SERVER_JOB_UPDATE](messages/3153_SERVER_JOB_UPDATE.md) | 2 |  |  |
| `0x3154` | [SERVER_JOB_DATA](messages/3154_SERVER_JOB_DATA.md) | 3 |  |  |
| `0x3156` | [SERVER_JOB_ALIAS](messages/3156_SERVER_JOB_ALIAS.md) | 4 | Yes |  |
| `0x3159` | [SERVER_COS_SPAWN](messages/3159_SERVER_COS_SPAWN.md) | 6 | Yes |  |
| `0x315A` | [SERVER_COS_UPDATE](messages/315A_SERVER_COS_UPDATE.md) | 4 |  |  |
| `0x315B` | [SERVER_COS_DATA](messages/315B_SERVER_COS_DATA.md) | 4 |  |  |
| `0x315C` | [SERVER_COS_REMOVE](messages/315C_SERVER_COS_REMOVE.md) | 2 |  |  |
| `0x315D` | [SERVER_COS_SETTINGS](messages/315D_SERVER_COS_SETTINGS.md) | 3 |  |  |
| `0x315E` | [SERVER_COS_INFO](messages/315E_SERVER_COS_INFO.md) | 2 |  |  |
| `0x3161` | [SERVER_COS_INFO_2](messages/3161_SERVER_COS_INFO_2.md) | 2 |  |  |
| `0x3200` | [SERVER_ENTITY_POSITION_UPDATE](messages/3200_SERVER_ENTITY_POSITION_UPDATE.md) | 3 |  |  |
| `0x3201` | [SERVER_ENTITY_GROUPSPAWN_DATA](messages/3201_SERVER_ENTITY_GROUPSPAWN_DATA.md) | 7 | Yes |  |
| `0x3206` | [SERVER_ENTITY_STATE_UPDATE](messages/3206_SERVER_ENTITY_STATE_UPDATE.md) | 3 |  |  |
| `0x3207` | [SERVER_ENTITY_DETAIL](messages/3207_SERVER_ENTITY_DETAIL.md) | 40 | Yes |  |
| `0x320A` | [SERVER_ENTITY_UPDATE_A](messages/320A_SERVER_ENTITY_UPDATE_A.md) | 3 |  |  |
| `0x320B` | [SERVER_ENTITY_UPDATE_B](messages/320B_SERVER_ENTITY_UPDATE_B.md) | 3 |  |  |
| `0x320C` | [SERVER_ENTITY_UPDATE_C](messages/320C_SERVER_ENTITY_UPDATE_C.md) | 2 |  |  |
| `0x3253` | [SERVER_ACADEMY_INFO](messages/3253_SERVER_ACADEMY_INFO.md) | 2 | Yes |  |
| `0x3254` | [SERVER_ACADEMY_DATA](messages/3254_SERVER_ACADEMY_DATA.md) | 0 | Yes |  |
| `0x3255` | [SERVER_ACADEMY_DATA_2](messages/3255_SERVER_ACADEMY_DATA_2.md) | 0 | Yes |  |
| `0x3256` | [SERVER_ACADEMY_UPDATE](messages/3256_SERVER_ACADEMY_UPDATE.md) | 6 | Yes |  |
| `0x3257` | [SERVER_ACADEMY_LIST](messages/3257_SERVER_ACADEMY_LIST.md) | 3 |  |  |
| `0x325C` | [SERVER_ARENA_DATA](messages/325C_SERVER_ARENA_DATA.md) | 3 | Yes |  |
| `0x325D` | [SERVER_ARENA_UPDATE](messages/325D_SERVER_ARENA_UPDATE.md) | 4 |  |  |
| `0x325E` | [SERVER_ARENA_RESULT](messages/325E_SERVER_ARENA_RESULT.md) | 4 |  |  |
| `0x325F` | [SERVER_ARENA_INFO](messages/325F_SERVER_ARENA_INFO.md) | 2 | Yes |  |
| `0x3261` | [SERVER_ARENA_SCORE](messages/3261_SERVER_ARENA_SCORE.md) | 5 |  |  |
| `0x3305` | [SERVER_ENTITY_TALK](messages/3305_SERVER_ENTITY_TALK.md) | 2 |  |  |
| `0x330F` | [SERVER_ENTITY_STAT_UPDATE](messages/330F_SERVER_ENTITY_STAT_UPDATE.md) | 6 | Yes |  |
| `0x3405` | [SERVER_GLOBAL_EVENT](messages/3405_SERVER_GLOBAL_EVENT.md) | 0 |  |  |
| `0x34A5` | [SERVER_EVENT_RESPONSE](messages/34A5_SERVER_EVENT_RESPONSE.md) | 0 |  |  |
| `0x34A6` | [SERVER_EVENT_ITEM](messages/34A6_SERVER_EVENT_ITEM.md) | 40 | Yes |  |
| `0x34AA` | [SERVER_EVENT_FLAG](messages/34AA_SERVER_EVENT_FLAG.md) | 3 |  |  |
| `0x34B1` | [SERVER_EVENT_ACTION](messages/34B1_SERVER_EVENT_ACTION.md) | 1 | Yes |  |
| `0x34B3` | [SERVER_EVENT_UPDATE](messages/34B3_SERVER_EVENT_UPDATE.md) | 2 | Yes |  |
| `0x34B4` | [SERVER_EVENT_DATA](messages/34B4_SERVER_EVENT_DATA.md) | 0 | Yes |  |
| `0x34B5` | [SERVER_EVENT_REWARD](messages/34B5_SERVER_EVENT_REWARD.md) | 2 |  |  |
| `0x34BE` | [SERVER_FORTRESS_DATA](messages/34BE_SERVER_FORTRESS_DATA.md) | 3 |  |  |
| `0x34D2` | [SERVER_FORTRESS_UPDATE](messages/34D2_SERVER_FORTRESS_UPDATE.md) | 1 | Yes |  |
| `0x34D5` | [SERVER_FORTRESS_INFO](messages/34D5_SERVER_FORTRESS_INFO.md) | 3 | Yes |  |
| `0x34E1` | [SERVER_FORTRESS_STATE](messages/34E1_SERVER_FORTRESS_STATE.md) | 2 | Yes |  |
| `0x34F2` | [SERVER_FORTRESS_ACTION](messages/34F2_SERVER_FORTRESS_ACTION.md) | 1 |  |  |
| `0x350D` | [SERVER_RANKING_DATA](messages/350D_SERVER_RANKING_DATA.md) | 24 | Yes |  |
| `0x3514` | [SERVER_RANKING_INFO](messages/3514_SERVER_RANKING_INFO.md) | 2 |  |  |
| `0x351E` | [SERVER_RANKING_UPDATE](messages/351E_SERVER_RANKING_UPDATE.md) | 2 | Yes |  |
| `0x3530` | [SERVER_BATTLE_DATA](messages/3530_SERVER_BATTLE_DATA.md) | 3 | Yes |  |
| `0x3532` | [SERVER_BATTLE_INFO](messages/3532_SERVER_BATTLE_INFO.md) | 2 |  |  |
| `0x3809` | [SERVER_TIME_UPDATE](messages/3809_SERVER_TIME_UPDATE.md) | 3 |  |  |
| `0x385F` | [SERVER_MAP_DATA](messages/385F_SERVER_MAP_DATA.md) | 4 |  |  |
| `0x3864` | [SERVER_WORLD_UPDATE](messages/3864_SERVER_WORLD_UPDATE.md) | 2 | Yes |  |
| `0x3908` | [SERVER_REGION_DATA](messages/3908_SERVER_REGION_DATA.md) | 6 | Yes |  |
| `0x3C80` | [SERVER_STALL_CREATE](messages/3C80_SERVER_STALL_CREATE.md) | 10 | Yes |  |
| `0x3C81` | [SERVER_STALL_UPDATE_DATA](messages/3C81_SERVER_STALL_UPDATE_DATA.md) | 26 | Yes |  |
| `0x3C86` | [SERVER_STALL_CLOSE](messages/3C86_SERVER_STALL_CLOSE.md) | 5 | Yes |  |
| `0x3C87` | [SERVER_STALL_PURCHASE](messages/3C87_SERVER_STALL_PURCHASE.md) | 13 | Yes |  |
| `0x3CA2` | [SERVER_EXCHANGE_DATA](messages/3CA2_SERVER_EXCHANGE_DATA.md) | 9 |  |  |

### Server → Client (Entity) (6 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0x7030` | [SERVER_CHAT_SYSTEM](messages/7030_SERVER_CHAT_SYSTEM.md) | 2 | Yes |  |
| `0x706D` | [SERVER_SOCIAL_DATA](messages/706D_SERVER_SOCIAL_DATA.md) | 15 | Yes |  |
| `0x7110` | [SERVER_FRIEND_DATA](messages/7110_SERVER_FRIEND_DATA.md) | 11 |  |  |
| `0x7302` | [SERVER_PARTY_UPDATE](messages/7302_SERVER_PARTY_UPDATE.md) | 2 | Yes |  |
| `0x747E` | [SERVER_GUILD_DATA](messages/747E_SERVER_GUILD_DATA.md) | 20 | Yes |  |
| `0x751A` | [SERVER_UNION_DATA](messages/751A_SERVER_UNION_DATA.md) | 6 | Yes |  |

### Client → Server (Game) (36 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0xB005` | [CLIENT_LOGIN_REQUEST](messages/B005_CLIENT_LOGIN_REQUEST.md) | 1 |  |  |
| `0xB006` | [CLIENT_AUTH_REQUEST](messages/B006_CLIENT_AUTH_REQUEST.md) | 3 | Yes |  |
| `0xB010` | [CLIENT_CHARACTER_SELECT](messages/B010_CLIENT_CHARACTER_SELECT.md) | 2 | Yes |  |
| `0xB021` | [CLIENT_CHARACTER_CREATE](messages/B021_CLIENT_CHARACTER_CREATE.md) | 1 |  |  |
| `0xB024` | [CLIENT_CHARACTER_LIST_REQUEST](messages/B024_CLIENT_CHARACTER_LIST_REQUEST.md) | 6 | Yes |  |
| `0xB025` | [CLIENT_CHARACTER_DELETE](messages/B025_CLIENT_CHARACTER_DELETE.md) | 2 |  |  |
| `0xB030` | [CLIENT_MOVEMENT_REQUEST](messages/B030_CLIENT_MOVEMENT_REQUEST.md) | 3 |  |  |
| `0xB031` | [CLIENT_MOVEMENT_CANCEL](messages/B031_CLIENT_MOVEMENT_CANCEL.md) | 2 | Yes |  |
| `0xB034` | [CLIENT_ENTITY_SELECT](messages/B034_CLIENT_ENTITY_SELECT.md) | 2 | Yes |  |
| `0xB03C` | [CLIENT_ENTITY_ACTION](messages/B03C_CLIENT_ENTITY_ACTION.md) | 5 | Yes |  |
| `0xB03E` | [CLIENT_ENTITY_INTERACT](messages/B03E_CLIENT_ENTITY_INTERACT.md) | 2 |  |  |
| `0xB03F` | [CLIENT_ENTITY_DESELECT](messages/B03F_CLIENT_ENTITY_DESELECT.md) | 2 | Yes |  |
| `0xB045` | [CLIENT_NPC_INTERACT](messages/B045_CLIENT_NPC_INTERACT.md) | 17 | Yes |  |
| `0xB046` | [CLIENT_NPC_RESPONSE](messages/B046_CLIENT_NPC_RESPONSE.md) | 3 |  |  |
| `0xB04B` | [CLIENT_GAME_OPTION](messages/B04B_CLIENT_GAME_OPTION.md) | 3 | Yes |  |
| `0xB04C` | [CLIENT_GAME_READY](messages/B04C_CLIENT_GAME_READY.md) | 1 |  |  |
| `0xB04F` | [CLIENT_UNIQUE_ID](messages/B04F_CLIENT_UNIQUE_ID.md) | 3 |  |  |
| `0xB050` | [CLIENT_CHAT_REQUEST](messages/B050_CLIENT_CHAT_REQUEST.md) | 2 | Yes |  |
| `0xB051` | [CLIENT_CHAT_CLEAR](messages/B051_CLIENT_CHAT_CLEAR.md) | 1 | Yes |  |
| `0xB059` | [CLIENT_EMOTE](messages/B059_CLIENT_EMOTE.md) | 4 |  |  |
| `0xB05A` | [CLIENT_SIT_STAND](messages/B05A_CLIENT_SIT_STAND.md) | 2 | Yes |  |
| `0xB05B` | [CLIENT_ENTITY_UPDATE_STATE](messages/B05B_CLIENT_ENTITY_UPDATE_STATE.md) | 2 | Yes |  |
| `0xB05D` | [CLIENT_SIEGE_REQUEST](messages/B05D_CLIENT_SIEGE_REQUEST.md) | 15 | Yes |  |
| `0xB05E` | [CLIENT_SIEGE_RESPONSE](messages/B05E_CLIENT_SIEGE_RESPONSE.md) | 0 |  |  |
| `0xB060` | [CLIENT_SIEGE_ACTION](messages/B060_CLIENT_SIEGE_ACTION.md) | 0 | Yes |  |
| `0xB062` | [CLIENT_WORLD_REQUEST](messages/B062_CLIENT_WORLD_REQUEST.md) | 23 | Yes |  |
| `0xB067` | [CLIENT_TELEPORT_REQUEST](messages/B067_CLIENT_TELEPORT_REQUEST.md) | 2 | Yes |  |
| `0xB069` | [CLIENT_TELEPORT_CONFIRM](messages/B069_CLIENT_TELEPORT_CONFIRM.md) | 2 | Yes |  |
| `0xB06A` | [CLIENT_ENTITY_SPAWN_REQUEST](messages/B06A_CLIENT_ENTITY_SPAWN_REQUEST.md) | 10 | Yes |  |
| `0xB06B` | [CLIENT_ENTITY_SPAWN_CONFIRM](messages/B06B_CLIENT_ENTITY_SPAWN_CONFIRM.md) | 10 | Yes |  |
| `0xB06C` | [CLIENT_ENTITY_DESPAWN_REQUEST](messages/B06C_CLIENT_ENTITY_DESPAWN_REQUEST.md) | 3 | Yes |  |
| `0xB06D` | [CLIENT_WORLD_SPAWN_REQUEST](messages/B06D_CLIENT_WORLD_SPAWN_REQUEST.md) | 24 |  |  |
| `0xB070` | [CLIENT_ENTITY_POSITION_REQUEST](messages/B070_CLIENT_ENTITY_POSITION_REQUEST.md) | 2 |  |  |
| `0xB071` | [CLIENT_ENTITY_DETAIL_REQUEST](messages/B071_CLIENT_ENTITY_DETAIL_REQUEST.md) | 17 | Yes |  |
| `0xB072` | [CLIENT_ENTITY_STATUS_REQUEST](messages/B072_CLIENT_ENTITY_STATUS_REQUEST.md) | 6 | Yes |  |
| `0xB074` | [CLIENT_ENTITY_INFO_REQUEST](messages/B074_CLIENT_ENTITY_INFO_REQUEST.md) | 2 | Yes |  |

### Client → Server (Extended) (63 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0xB081` | [CLIENT_INVENTORY_REQUEST](messages/B081_CLIENT_INVENTORY_REQUEST.md) | 3 | Yes |  |
| `0xB082` | [CLIENT_INVENTORY_MOVE](messages/B082_CLIENT_INVENTORY_MOVE.md) | 2 |  |  |
| `0xB083` | [CLIENT_INVENTORY_USE](messages/B083_CLIENT_INVENTORY_USE.md) | 1 | Yes |  |
| `0xB084` | [CLIENT_INVENTORY_DROP](messages/B084_CLIENT_INVENTORY_DROP.md) | 1 | Yes |  |
| `0xB0A1` | [CLIENT_SKILL_REQUEST](messages/B0A1_CLIENT_SKILL_REQUEST.md) | 3 | Yes |  |
| `0xB0A2` | [CLIENT_SKILL_USE](messages/B0A2_CLIENT_SKILL_USE.md) | 2 | Yes |  |
| `0xB0A7` | [CLIENT_PARTY_REQUEST](messages/B0A7_CLIENT_PARTY_REQUEST.md) | 3 |  |  |
| `0xB0B2` | [CLIENT_PARTY_INVITE](messages/B0B2_CLIENT_PARTY_INVITE.md) | 4 |  |  |
| `0xB0B3` | [CLIENT_PARTY_DATA](messages/B0B3_CLIENT_PARTY_DATA.md) | 31 | Yes |  |
| `0xB0B4` | [CLIENT_PARTY_RESPONSE](messages/B0B4_CLIENT_PARTY_RESPONSE.md) | 4 | Yes |  |
| `0xB0B5` | [CLIENT_PARTY_UPDATE](messages/B0B5_CLIENT_PARTY_UPDATE.md) | 48 | Yes |  |
| `0xB0BA` | [CLIENT_GUILD_REQUEST](messages/B0BA_CLIENT_GUILD_REQUEST.md) | 2 | Yes |  |
| `0xB0BD` | [CLIENT_STORAGE_REQUEST](messages/B0BD_CLIENT_STORAGE_REQUEST.md) | 3 |  |  |
| `0xB0BE` | [CLIENT_STORAGE_ACTION](messages/B0BE_CLIENT_STORAGE_ACTION.md) | 2 | Yes |  |
| `0xB0C0` | [CLIENT_PET_REQUEST](messages/B0C0_CLIENT_PET_REQUEST.md) | 2 | Yes |  |
| `0xB0C5` | [CLIENT_PET_ACTION](messages/B0C5_CLIENT_PET_ACTION.md) | 1 | Yes |  |
| `0xB0C6` | [CLIENT_NPC_DATA_REQUEST](messages/B0C6_CLIENT_NPC_DATA_REQUEST.md) | 13 |  |  |
| `0xB0C7` | [CLIENT_NPC_CLOSE](messages/B0C7_CLIENT_NPC_CLOSE.md) | 1 |  |  |
| `0xB0CB` | [CLIENT_QUEST_REQUEST](messages/B0CB_CLIENT_QUEST_REQUEST.md) | 3 | Yes |  |
| `0xB0D8` | [CLIENT_STALL_REQUEST](messages/B0D8_CLIENT_STALL_REQUEST.md) | 14 |  |  |
| `0xB0D9` | [CLIENT_STALL_UPDATE](messages/B0D9_CLIENT_STALL_UPDATE.md) | 3 | Yes |  |
| `0xB0DB` | [CLIENT_ALCHEMY_REQUEST](messages/B0DB_CLIENT_ALCHEMY_REQUEST.md) | 2 |  |  |
| `0xB0E1` | [CLIENT_EXCHANGE_REQUEST](messages/B0E1_CLIENT_EXCHANGE_REQUEST.md) | 3 |  | character class, job/trade system |
| `0xB0E2` | [CLIENT_EXCHANGE_CONFIRM](messages/B0E2_CLIENT_EXCHANGE_CONFIRM.md) | 4 | Yes |  |
| `0xB0E3` | [CLIENT_EXCHANGE_APPROVE](messages/B0E3_CLIENT_EXCHANGE_APPROVE.md) | 1 | Yes |  |
| `0xB0E4` | [CLIENT_TITLE_REQUEST](messages/B0E4_CLIENT_TITLE_REQUEST.md) | 6 | Yes |  |
| `0xB0E5` | [CLIENT_ENTITY_EQUIPMENT](messages/B0E5_CLIENT_ENTITY_EQUIPMENT.md) | 16 | Yes |  |
| `0xB0E6` | [CLIENT_ITEM_REQUEST](messages/B0E6_CLIENT_ITEM_REQUEST.md) | 3 | Yes |  |
| `0xB0EA` | [CLIENT_ENTITY_GOLD](messages/B0EA_CLIENT_ENTITY_GOLD.md) | 1 |  |  |
| `0xB0ED` | [CLIENT_ENTITY_UPDATE](messages/B0ED_CLIENT_ENTITY_UPDATE.md) | 5 | Yes |  |
| `0xB0F1` | [CLIENT_ENTITY_DETAIL_DATA](messages/B0F1_CLIENT_ENTITY_DETAIL_DATA.md) | 29 | Yes |  |
| `0xB0F2` | [CLIENT_ENTITY_UPDATE_DATA](messages/B0F2_CLIENT_ENTITY_UPDATE_DATA.md) | 1 |  |  |
| `0xB0F3` | [CLIENT_ENTITY_FULL_DATA](messages/B0F3_CLIENT_ENTITY_FULL_DATA.md) | 28 | Yes |  |
| `0xB0F4` | [CLIENT_ENTITY_STATUS](messages/B0F4_CLIENT_ENTITY_STATUS.md) | 1 | Yes |  |
| `0xB0F6` | [CLIENT_ENTITY_SP](messages/B0F6_CLIENT_ENTITY_SP.md) | 2 | Yes |  |
| `0xB0F8` | [CLIENT_ENTITY_RESURRECT](messages/B0F8_CLIENT_ENTITY_RESURRECT.md) | 1 | Yes |  |
| `0xB0F9` | [CLIENT_ENTITY_DETAIL_DATA_2](messages/B0F9_CLIENT_ENTITY_DETAIL_DATA_2.md) | 27 |  |  |
| `0xB0FA` | [CLIENT_ENTITY_XP](messages/B0FA_CLIENT_ENTITY_XP.md) | 2 | Yes |  |
| `0xB0FB` | [CLIENT_ENTITY_GUILD](messages/B0FB_CLIENT_ENTITY_GUILD.md) | 2 | Yes |  |
| `0xB0FC` | [CLIENT_ENTITY_REGION](messages/B0FC_CLIENT_ENTITY_REGION.md) | 12 |  |  |
| `0xB0FD` | [CLIENT_ENTITY_PVP](messages/B0FD_CLIENT_ENTITY_PVP.md) | 2 | Yes |  |
| `0xB0FF` | [CLIENT_BERSERK_REQUEST](messages/B0FF_CLIENT_BERSERK_REQUEST.md) | 3 | Yes |  |
| `0xB103` | [CLIENT_JOB_REQUEST](messages/B103_CLIENT_JOB_REQUEST.md) | 1 | Yes |  |
| `0xB104` | [CLIENT_JOB_ACTION](messages/B104_CLIENT_JOB_ACTION.md) | 1 | Yes |  |
| `0xB105` | [CLIENT_JOB_DATA](messages/B105_CLIENT_JOB_DATA.md) | 2 | Yes |  |
| `0xB106` | [CLIENT_JOB_UPDATE](messages/B106_CLIENT_JOB_UPDATE.md) | 2 | Yes |  |
| `0xB107` | [CLIENT_JOB_DETAIL](messages/B107_CLIENT_JOB_DETAIL.md) | 13 | Yes |  |
| `0xB110` | [CLIENT_COS_REQUEST](messages/B110_CLIENT_COS_REQUEST.md) | 6 |  |  |
| `0xB112` | [CLIENT_COS_ACTION](messages/B112_CLIENT_COS_ACTION.md) | 4 | Yes |  |
| `0xB113` | [CLIENT_COS_DATA](messages/B113_CLIENT_COS_DATA.md) | 2 | Yes |  |
| `0xB114` | [CLIENT_COS_UPDATE](messages/B114_CLIENT_COS_UPDATE.md) | 2 | Yes |  |
| `0xB116` | [CLIENT_COS_INFO](messages/B116_CLIENT_COS_INFO.md) | 4 | Yes |  |
| `0xB119` | [CLIENT_ACADEMY_REQUEST](messages/B119_CLIENT_ACADEMY_REQUEST.md) | 2 |  |  |
| `0xB11A` | [CLIENT_ACADEMY_DATA](messages/B11A_CLIENT_ACADEMY_DATA.md) | 2 |  |  |
| `0xB121` | [CLIENT_ARENA_REQUEST](messages/B121_CLIENT_ARENA_REQUEST.md) | 3 |  |  |
| `0xB150` | [CLIENT_ENTITY_DETAIL_2](messages/B150_CLIENT_ENTITY_DETAIL_2.md) | 1 | Yes |  |
| `0xB151` | [CLIENT_ENTITY_SPAWN_DATA](messages/B151_CLIENT_ENTITY_SPAWN_DATA.md) | 41 | Yes |  |
| `0xB155` | [CLIENT_ENTITY_SPAWN_INFO](messages/B155_CLIENT_ENTITY_SPAWN_INFO.md) | 0 |  |  |
| `0xB157` | [CLIENT_JOB_ALIAS_DATA](messages/B157_CLIENT_JOB_ALIAS_DATA.md) | 4 | Yes |  |
| `0xB15F` | [CLIENT_COS_REMOVE](messages/B15F_CLIENT_COS_REMOVE.md) | 2 |  |  |
| `0xB160` | [CLIENT_ARENA_ACTION](messages/B160_CLIENT_ARENA_ACTION.md) | 3 | Yes |  |
| `0xB168` | [CLIENT_ARENA_DATA](messages/B168_CLIENT_ARENA_DATA.md) | 4 |  |  |
| `0xB16A` | [CLIENT_ENTITY_SPAWN_UPDATE](messages/B16A_CLIENT_ENTITY_SPAWN_UPDATE.md) | 40 | Yes |  |

### Client → Server (Extended 2) (46 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0xB202` | [CLIENT_SKILL_DATA](messages/B202_CLIENT_SKILL_DATA.md) | 3 | Yes |  |
| `0xB203` | [CLIENT_SKILL_UPDATE](messages/B203_CLIENT_SKILL_UPDATE.md) | 3 | Yes |  |
| `0xB250` | [CLIENT_ACADEMY_UPDATE](messages/B250_CLIENT_ACADEMY_UPDATE.md) | 2 | Yes |  |
| `0xB251` | [CLIENT_ACADEMY_DETAIL](messages/B251_CLIENT_ACADEMY_DETAIL.md) | 5 | Yes |  |
| `0xB252` | [CLIENT_ACADEMY_ACTION](messages/B252_CLIENT_ACADEMY_ACTION.md) | 0 | Yes |  |
| `0xB256` | [CLIENT_ARENA_UPDATE](messages/B256_CLIENT_ARENA_UPDATE.md) | 6 | Yes |  |
| `0xB258` | [CLIENT_ARENA_DETAIL](messages/B258_CLIENT_ARENA_DETAIL.md) | 5 | Yes |  |
| `0xB259` | [CLIENT_ARENA_INFO](messages/B259_CLIENT_ARENA_INFO.md) | 2 | Yes |  |
| `0xB25A` | [CLIENT_ARENA_STATUS](messages/B25A_CLIENT_ARENA_STATUS.md) | 2 | Yes |  |
| `0xB302` | [CLIENT_PARTY_DETAIL](messages/B302_CLIENT_PARTY_DETAIL.md) | 6 |  |  |
| `0xB304` | [CLIENT_PARTY_MEMBER](messages/B304_CLIENT_PARTY_MEMBER.md) | 5 | Yes |  |
| `0xB308` | [CLIENT_GUILD_REQUEST_2](messages/B308_CLIENT_GUILD_REQUEST_2.md) | 7 | Yes |  |
| `0xB309` | [CLIENT_GUILD_UPDATE](messages/B309_CLIENT_GUILD_UPDATE.md) | 5 | Yes |  |
| `0xB30A` | [CLIENT_GUILD_ACTION](messages/B30A_CLIENT_GUILD_ACTION.md) | 2 | Yes |  |
| `0xB30B` | [CLIENT_GUILD_DATA](messages/B30B_CLIENT_GUILD_DATA.md) | 4 |  |  |
| `0xB30C` | [CLIENT_GUILD_INFO](messages/B30C_CLIENT_GUILD_INFO.md) | 2 | Yes |  |
| `0xB30D` | [CLIENT_GUILD_DETAIL](messages/B30D_CLIENT_GUILD_DETAIL.md) | 5 | Yes |  |
| `0xB461` | [CLIENT_FORTRESS_REQUEST](messages/B461_CLIENT_FORTRESS_REQUEST.md) | 4 | Yes |  |
| `0xB462` | [CLIENT_FORTRESS_ACTION](messages/B462_CLIENT_FORTRESS_ACTION.md) | 2 | Yes |  |
| `0xB463` | [CLIENT_FORTRESS_DATA](messages/B463_CLIENT_FORTRESS_DATA.md) | 1 | Yes |  |
| `0xB470` | [CLIENT_STALL_BROWSE](messages/B470_CLIENT_STALL_BROWSE.md) | 2 | Yes |  |
| `0xB471` | [CLIENT_STALL_BUY](messages/B471_CLIENT_STALL_BUY.md) | 25 |  |  |
| `0xB472` | [CLIENT_STALL_ACTION](messages/B472_CLIENT_STALL_ACTION.md) | 3 | Yes |  |
| `0xB473` | [CLIENT_STALL_CLOSE](messages/B473_CLIENT_STALL_CLOSE.md) | 2 | Yes |  |
| `0xB474` | [CLIENT_STALL_UPDATE_2](messages/B474_CLIENT_STALL_UPDATE_2.md) | 2 | Yes |  |
| `0xB475` | [CLIENT_STALL_INFO](messages/B475_CLIENT_STALL_INFO.md) | 2 | Yes |  |
| `0xB476` | [CLIENT_STALL_DATA](messages/B476_CLIENT_STALL_DATA.md) | 2 | Yes |  |
| `0xB477` | [CLIENT_STALL_DETAIL](messages/B477_CLIENT_STALL_DETAIL.md) | 2 | Yes |  |
| `0xB478` | [CLIENT_STALL_CONFIRM](messages/B478_CLIENT_STALL_CONFIRM.md) | 2 | Yes |  |
| `0xB47A` | [CLIENT_STALL_RESPONSE](messages/B47A_CLIENT_STALL_RESPONSE.md) | 1 |  |  |
| `0xB47B` | [CLIENT_RANKING_REQUEST](messages/B47B_CLIENT_RANKING_REQUEST.md) | 8 | Yes |  |
| `0xB47C` | [CLIENT_RANKING_ACTION](messages/B47C_CLIENT_RANKING_ACTION.md) | 7 | Yes |  |
| `0xB47D` | [CLIENT_RANKING_DATA](messages/B47D_CLIENT_RANKING_DATA.md) | 3 | Yes |  |
| `0xB483` | [CLIENT_BATTLE_REQUEST](messages/B483_CLIENT_BATTLE_REQUEST.md) | 1 |  |  |
| `0xB4D4` | [CLIENT_FORTRESS_UPDATE](messages/B4D4_CLIENT_FORTRESS_UPDATE.md) | 6 | Yes |  |
| `0xB506` | [CLIENT_RANKING_DETAIL](messages/B506_CLIENT_RANKING_DETAIL.md) | 5 | Yes |  |
| `0xB507` | [CLIENT_RANKING_UPDATE](messages/B507_CLIENT_RANKING_UPDATE.md) | 11 | Yes |  |
| `0xB508` | [CLIENT_RANKING_INFO](messages/B508_CLIENT_RANKING_INFO.md) | 1 | Yes |  |
| `0xB509` | [CLIENT_RANKING_LIST](messages/B509_CLIENT_RANKING_LIST.md) | 10 | Yes |  |
| `0xB50A` | [CLIENT_RANKING_ENTRY](messages/B50A_CLIENT_RANKING_ENTRY.md) | 24 | Yes |  |
| `0xB50B` | [CLIENT_RANKING_FULL](messages/B50B_CLIENT_RANKING_FULL.md) | 38 |  |  |
| `0xB516` | [CLIENT_BATTLE_ACTION](messages/B516_CLIENT_BATTLE_ACTION.md) | 5 | Yes |  |
| `0xB519` | [CLIENT_BATTLE_DATA](messages/B519_CLIENT_BATTLE_DATA.md) | 13 | Yes |  |
| `0xB51A` | [CLIENT_BATTLE_UPDATE](messages/B51A_CLIENT_BATTLE_UPDATE.md) | 5 |  |  |
| `0xB51C` | [CLIENT_BATTLE_INFO](messages/B51C_CLIENT_BATTLE_INFO.md) | 2 | Yes |  |
| `0xB51D` | [CLIENT_BATTLE_DETAIL](messages/B51D_CLIENT_BATTLE_DETAIL.md) | 2 | Yes |  |

### Server Notifications (1 messages)

| Opcode | Name | Fields | Conditional | Domain |
|--------|------|--------|-------------|--------|
| `0x5000` | [HANDSHAKE](messages/5000_HANDSHAKE.md) | 5 |  |  |

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
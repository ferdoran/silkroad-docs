# Game Enums and Constants

Constants and enum values extracted from assert expressions and debug strings in the client binary.

## Vital Info Mask

Used in entity status updates (e.g., `0xB045`). Bitmask for `byMask` field.

| Constant | Context |
|----------|---------|
| `VITAL_INFO_MP` | `!(byMask & VITAL_INFO_MP)` |
| `VITAL_INFO_ABNORMAL` | `!(byMask & VITAL_INFO_ABNORMAL)` |

## Party Leave Reasons

Debug format strings for party member departure.

| Constant | Usage |
|----------|-------|
| `LEAVE_PARTY_BOOTED` | `LEAVE_PARTY_BOOTED %X` — Kicked from party |
| `LEAVE_PARTY_SECEDE` | `LEAVE_PARTY_SECEDE %X` — Left voluntarily |
| `LEAVE_PARTY_LOGOUT` | `LEAVE_PARTY_LOGOUT %X` — Logged out |
| `LEAVE_PARTY_SERVER_MIGRATION` | `LEAVE_PARTY_SERVER_MIGRATION %X` — Server transfer |

## Party Job Types

| Constant | Usage |
|----------|-------|
| `PARTY_JOB_ADD_MEMBER` | `PARTY_JOB_ADD_MEMBER %X` |

## Skill Window Types

Used for `m_bySkillWndType` comparison in skill handlers.

| Constant | Context |
|----------|---------|
| `SKILLWND_TYPE_CIRCULAR_GROWUP` | Circular growth skill tree |
| `SKILLWND_TYPE_WITHDRAWAL` | Skill withdrawal/removal |

## Item Constants

| Constant | Context |
|----------|---------|
| `MAX_MAGPARAM_PER_ITEM` | `m_btMagicParamNum <= MAX_MAGPARAM_PER_ITEM` — Max magic options per item |
| `EQUIP_VISUAL_COUNT` | `dwSlotPos < EQUIP_VISUAL_COUNT` — Number of visible equipment slots |
| `AUTO_POTION_COUNT` | `byType < AUTO_POTION_COUNT` — Number of auto-potion types |

## Payment Types

| Constant | Context |
|----------|---------|
| `PAYMENT_DEVICE_GOLDPRICE` | `pWSR->GetGold() >= pSO->m_sCost.Cost[PAYMENT_DEVICE_GOLDPRICE]` |

## Inventory Constants

| Constant | Context |
|----------|---------|
| `MAX_INVENTORY_TAB_NUM` | `byTabNum <= MAX_INVENTORY_TAB_NUM` |
| `N_MAX_QUICKSLOT` | `byIndexSot < N_MAX_QUICKSLOT` |

## Item Type IDs

From data references in assert strings:

| Constant | Meaning |
|----------|---------|
| `ITEM_ETC_E` | Etc item type (European) |
| `ITEM_QCX` | Quest item CX |
| `ITEM_QNO` | Quest item NO |
| `ITEM_QSP` | Quest item SP |
| `ITEM_QTUTORIAL` | Tutorial quest item |

## Status Effect Parameters

From sub-function string analysis in NPC interaction handlers:

| Constant | Icon | Effect |
|----------|------|--------|
| `PARAM_RESTRICTION` | — | Movement restriction |
| `PARAM_WEAKLY` | — | Weakened state |
| `PARAM_CURSING` | — | Cursed state |
| `PARAM_ETC` | — | Other status effects |

### Status Effect Icons

| Effect | Icon Path |
|--------|-----------|
| Frostbite | `icon\stateodd\s_frostbite_icon.ddj` |
| Freeze | `icon\stateodd\s_freeze_icon.ddj` |
| Burn | `icon\stateodd\s_burn_icon.ddj` |
| Electric Shock | `icon\stateodd\s_electricshock_icon.ddj` |
| Poisoning | `icon\stateodd\s_poisoning_icon.ddj` |
| Zombie | `icon\stateodd\s_zombi_icon.ddj` |
| Root | `icon\stateodd\s_root_icon.ddj` |

## Teleport

From debug format string:

```
TELEPORTGATE -> Type(%d), Target(%d)
```

Fields: `byType` (teleport type), `dwTarget` (destination ID).

## File Type Constants

| Constant | Context |
|----------|---------|
| `SEEKFILE_TYPE_NUM` | `dwLoadType < SEEKFILE_TYPE_NUM` — Number of seekable file types |

## Key Member Variables

From assert expressions, these reveal the internal struct layout:

| Variable | Type | Context |
|----------|------|---------|
| `pM->dwRealTime` | `u32` | Server real time |
| `pM->m_wDay` | `u16` | Day value |
| `pM->m_byHour` | `u8` | Hour value |
| `pM->m_byMin` | `u8` | Minute value |
| `m_dwCurActiveMasteryID` | `u32` | Currently active mastery |
| `m_btMagicParamNum` | `u8` | Magic parameter count |
| `m_bySkillWndType` | `u8` | Skill window type |
| `m_bDealing` | `bool` | Currently trading |
| `m_strAlias` | `string` | Job alias |
| `m_nReq_Sp` | `int` | Required SP for skill |
| `m_sTID.wTypeID` | `u16` | Item type ID |
| `m_blValid` | `bool` | Item validity |

## RTTI Class Hierarchy (Network)

| Class | Purpose |
|-------|---------|
| `CSession` | Network session management |
| `CMsgStreamBuffer` | Message serialization buffer |
| `CClientMsg` | Client message type |
| `CMassiveMsg` | Massive/broadcast message |
| `CMsgHandler` | Message dispatch handler |
| `CMsgHooker` | Message hook system |
| `CNetProcessIn` | Incoming message processor |
| `CClientProcess` | Client-side message processor (vtable handlers) |
| `CInterfaceNetSender` | Outgoing message builder |
| `CNetEngine` | Network engine core |
| `CStallNetworkData` | Stall network data struct |
| `CEntityManagerClient` | Client entity manager |

## Source File to Handler Mapping

| Source File | Handler Domain |
|-------------|---------------|
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

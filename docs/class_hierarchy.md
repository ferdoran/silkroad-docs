# Client Class Hierarchy

RTTI (Run-Time Type Information) analysis of `sro_client.exe` reveals **899** C++ classes.
This page documents the key class hierarchies organized by subsystem.

## Network Subsystem

### Core Network

| Class | Purpose |
|-------|---------|
| `CSession` | Network session management, message send/receive |
| `CNetEngine` | Network engine core |
| `CBaseSocket` | Base socket abstraction |
| `CSockStream` | TCP stream socket |
| `CSockDatagram` | UDP datagram socket |
| `CSockListener` | Server socket listener |
| `CSockSystem` | Socket system initialization |
| `CClientNet` / `IClientNet` | Client network interface |
| `CBlowFish` | Blowfish encryption |
| `CKeyExchangeBase` | Key exchange base |
| `CKeySender` / `CKeyRepicient` | Key exchange sender/recipient |

### Message System

| Class | Purpose |
|-------|---------|
| `CMsgStreamBuffer` | Message serialization buffer (Init/Write/Read/Destroy) |
| `CClientMsg` | Client message type |
| `CMassiveMsg` | Broadcast/massive message |
| `CMsgHandler` | Message dispatch handler |
| `CMsgHooker` | Message hook system |
| `CBuffer` | Generic data buffer |
| `CMemBufManager` | Memory buffer pool manager |

### Message Processing

| Class | Purpose |
|-------|---------|
| `CNetProcessIn` | Incoming message processor (base) |
| `CNetProcessSecond` | Secondary message processor |
| `CNetProcessThird` | Tertiary message processor |
| `CClientProcess` | Client-side message processor (vtable handlers) |
| `CInterfaceNetSender` | Outgoing message builder |
| `CProcess` | Base process class |

## Entity Subsystem

### Entity Hierarchy

```
CIEntity (base)
├── CICharactor (character base)
│   ├── CICUser (player character)
│   │   └── CICPlayer (local player)
│   ├── CICNonuser (NPCs base)
│   │   ├── CICNPC (NPC)
│   │   ├── CICMonster (monster)
│   │   │   └── CICMonsterNPC (monster with NPC behavior)
│   │   └── CICGuard (guard NPC)
│   ├── CICCos (COS - pet/transport)
│   │   └── CICRide (rideable mount)
│   └── CICScriptObj (scripted object)
├── CIObject (world object base)
│   ├── CIItem (dropped item)
│   ├── CIOBillboard (billboard)
│   ├── CIODecal (ground decal)
│   └── CITeleportGate (teleport gate)
├── CIDecoMoveObj (moving decoration)
├── CIDecoStopObj (static decoration)
├── CIDecoSkill (skill visual effect)
├── CIDecoAppear (appear effect)
├── CIDecoDisappear (disappear effect)
├── CIDecoDamageEffect (damage number)
├── CIDamageText (damage text display)
├── CISkillObj (skill object)
└── CIParticleObj (particle)
```

### Entity Management

| Class | Purpose |
|-------|---------|
| `CEntityManager` | Base entity manager |
| `CEntityManagerClient` | Client entity manager |
| `CICScriptObjManager` | Script object manager |
| `CIDPool` | Entity ID pool |
| `CNavigatedObject` | Object with navigation |
| `CNavigationDeadreckon` | Dead reckoning for movement prediction |

## UI/Interface Subsystem

### Base UI Classes

```
CGWndBase
└── CGWnd
    └── CIFWnd (interface window base)
        ├── CIFFrame (framed window)
        ├── CIFButton (button)
        ├── CIFStatic (static text/image)
        ├── CIFEdit (text input)
        ├── CIFListCtrl (list control)
        ├── CIFGauge (progress bar)
        ├── CIFSlot (item/skill slot)
        ├── CIFCheckBox (checkbox)
        ├── CIFComboBox (dropdown)
        ├── CIFScrollBar (scrollbar)
        └── CIFPopupWnd (popup window)
```

### Game UI Windows

| Class | Purpose |
|-------|---------|
| `CGInterface` / `CGIGInterface` | Global interface manager |
| `CIFMainFrame` / `CNIFMainFrame` | Main game frame |
| `CIFMainPopup` | Main popup menu |
| `CIFUnderBar` | Bottom action bar |
| `CIFInventory` | Inventory window |
| `CIFEquipment` | Equipment window |
| `CIFCharacterWnd` | Character stats window |
| `CIFSkill` | Skill window |
| `CIFSkillBoard` | Skill tree board |
| `CIFSkillMastery` | Mastery tree |
| `CIFMinimap` | Minimap |
| `CIFWorldMap` | World map |
| `CIFQuest` | Quest log |
| `CIFChatViewer` | Chat display |
| `CIFChatModule` | Chat input module |
| `CIFParty` | Party window |
| `CIFExchange` | Player trade window |
| `CIFStall` | Player stall/shop |
| `CIFStore` | NPC store |
| `CIFOption` | Game options |
| `CIFLoading` | Loading screen |
| `CIFConsole` | Debug console |
| `CIF_NPCTalk` / `CIF_NPCWindow` | NPC dialog |
| `CIFTargetWindow` | Target info (base) |
| `CIFTargetWindowPlayer` | Player target info |
| `CIFTargetWindowJobPlayer` | Job player target info |
| `CIFTargetWindowCommonEnemy` | Enemy target info |
| `CIFTargetWindowSpecialMob` | Special mob target info |
| `CIFTargetWindowFortressStructure` | Fortress structure target |
| `CIFMessageBox` | Message box |
| `CIFConfirmbox` | Confirmation dialog |
| `CIFBuffViewer` | Buff/debuff display |
| `CIFAutoPotion` | Auto-potion settings |

### Guild UI

| Class | Purpose |
|-------|---------|
| `CNIFGuildWnd` | Guild window |
| `CNIFGuildIntroWnd` | Guild introduction |
| `CNIFGuildNotifyView` | Guild notices |
| `CNIFGuildGrantPow` | Guild permission grant |
| `CNIFGuildUserSlot` | Guild member slot |
| `CIFGuildLevelUp` | Guild level up |
| `CIFGuildPointUp` | Guild point up |
| `CIFGuildMasterElection` | Guild master election |
| `CIFGuildMasterLeave` | Guild master leaving |
| `CIFGuildPositionGrant` | Guild position grant |
| `CIFGuildSummonReq` | Guild summon request |
| `CIFGuildWar` | Guild war |
| `CIFRequestGuildWar` | Request guild war |
| `CNIFAllianceGuild` | Alliance guild |
| `CNIFHostileGuild` | Hostile guild |

### Fortress UI

| Class | Purpose |
|-------|---------|
| `CIFFortressMap` | Fortress map |
| `CIFFortressMapFrame` | Fortress map frame |
| `CIFFortressWarApplyWnd` | Fortress war application |
| `CIFFortressBusiness` | Fortress commerce |
| `CIFFortressMakeItemWnd` | Fortress item crafting |
| `CIFTaxManagement` | Tax management |

### Battle Arena UI

| Class | Purpose |
|-------|---------|
| `CNIFBattleArenaGuildWnd` | Battle arena guild |
| `CNIFBattleArenaRankWnd` | Battle arena rankings |
| `CNIFBattleArenaResultWnd` | Battle arena results |
| `CNIFBattleArenaRuleWnd` | Battle arena rules |
| `CNIFBattleArenaScoreWnd` | Battle arena scores |
| `CNIFFreeBattlePvp` | Free battle PvP |

### Item Mall / Cash Shop

| Class | Purpose |
|-------|---------|
| `CIFItemMall` | Item mall (base) |
| `CIFItemMallMain` | Item mall main page |
| `CIFItemMallShop` | Item mall shop |
| `CIFItemMallInventory` | Item mall inventory |
| `CIFItemMallMyInfo` | Item mall account info |
| `CIFItemMallPremium` | Premium items |
| `CIFItemMallPet` | Pet items |
| `CIFItemMallAvata` | Avatar/cosmetic items |
| `CIFItemMallAlchemy` | Alchemy items |
| `CIFItemMallConsumption` | Consumable items |
| `CIFItemMallHotStore` | Hot/featured items |
| `CIFItemMallTrunk` | Item mall storage |
| `CIFNewItemMall` | New item mall version |

### COS (Companion Object System) UI

| Class | Purpose |
|-------|---------|
| `CIFCOS` | COS base window |
| `CIFCOSCommand` | COS command interface |
| `CIFCOSInfo` | COS info display |
| `CIFCOSInventory` | COS inventory |
| `CIFCOSManager` | COS management |
| `CIFCOSSetup` | COS settings |
| `CIFCOSStatus` | COS status display |
| `CIFPetMiniInfo` | Pet mini-info popup |

## Game Data Subsystem

### Data Managers

| Class | Purpose |
|-------|---------|
| `CGlobalDataManager` | Global game data manager |
| `CCharacterData` | Character data definitions |
| `CCharacterDependentData` | Character-dependent data |
| `CSkillData` | Skill definitions |
| `CSkillGroupData` | Skill group definitions |
| `CMasteryData` | Mastery definitions |
| `CItemData` | Item definitions |
| `CSOItem` / `CSObject` | Service object (item instance) |
| `CQuestData` | Quest definitions |
| `CQuestRewardData` | Quest reward data |
| `CMagicOptionData` | Magic option (stats on items) |
| `CLevelData` | Level experience data |
| `CLevelGoldData` | Level gold data |
| `CTeleportData` | Teleport definitions |
| `CTeleportLink` | Teleport connections |
| `CNPCPosData` | NPC position data |
| `CWorldMapGuideData` | World map guide |

### Game System Managers

| Class | Purpose |
|-------|---------|
| `CInventoryManager` | Inventory management |
| `CGuildManager` | Guild management |
| `CQuestManager` | Quest management |
| `CAlchemyMgr` | Alchemy system |
| `CAlchemyMgrReinforce` | Alchemy reinforcement |
| `CAlchemyMgrManufacturing` | Alchemy manufacturing |
| `CAlchemyMgrDecompEquipment` | Alchemy decompose equipment |
| `CAlchemyMgrDecompAccessory` | Alchemy decompose accessory |
| `CCOSDataMgr` | COS data management |
| `CBattleArenaMgr` | Battle arena management |
| `CDropItemManager` | Drop item management |
| `CSkillCoolTimeManager` | Skill cooldown tracking |
| `CSkillRunTimeManager` | Skill runtime management |
| `CItemReuseDelayManager` | Item cooldown tracking |
| `CAutoPotion` | Auto-potion system |
| `CPartyRegData` / `CPartyRegDataMgr` | Party registration |
| `CCustomInfoManager` | Custom info management |
| `CEventGuideManager` | Event guide system |

### Shop/Trade System

| Class | Purpose |
|-------|---------|
| `CShopData` | Shop definition |
| `CShopGroupData` | Shop group |
| `CShopItemData` | Shop item |
| `CShopTabData` | Shop tab |
| `CRefShopdata` | Reference shop data |
| `CRefShopGoodsData` | Reference shop goods |
| `CRefPricePolicyOfItem` | Item pricing policy |
| `CStallNetworkData` | Player stall network data |
| `CIFStallNetwork` | Stall network handler |
| `CIFSpecialtyDeal` | Specialty trade deals |

## Rendering Subsystem

### 3D Engine

| Class | Purpose |
|-------|---------|
| `CD3DApplication` | Direct3D application base |
| `CD3DEnumeration` | D3D device enumeration |
| `CObj` | Base 3D object |
| `CObjRenderer` / `IObjRenderer` | Object renderer |
| `CObjRendererVS` | Vertex shader renderer |
| `CShader` | Shader program |
| `CShaderBlock` | Shader block |
| `CShaderBlockManager` | Shader manager |
| `CVertexShader` | Vertex shader |
| `CTextureRuntime` | Runtime texture |
| `CFrustum` / `IFrustum` | View frustum |
| `CVisibleChecker` / `IVisibleChecker` | Visibility testing |
| `CScreenDistortion` / `IScreenDistortion` | Screen distortion effect |

### Model/Primitive System

```
IPrim (interface)
└── CPrim (base primitive)
    ├── CPrimMesh (mesh data)
    ├── CPrimBone (bone data)
    ├── CPrimAnimation (animation data)
    ├── CPrimBranch (scene graph branch)
    ├── CPrimDummy (dummy/locator)
    ├── CPrimMtrl (material)
    ├── CPrimMtrlSet (material set)
    ├── CPrimTexture (texture reference)
    ├── CPrimSound (sound attachment)
    └── CPrimNode (scene graph node)
```

### Runtime Model System

| Class | Purpose |
|-------|---------|
| `CRTMesh` / `CRTMeshDynamic` | Runtime mesh |
| `CRTBone` | Runtime bone |
| `CRTSkeleton` | Runtime skeleton |
| `CRTAnimation` | Runtime animation (base) |
| `CRTAniCyclic` | Cyclic animation |
| `CRTAniOneShot` | One-shot animation |
| `CRTGeometry` | Runtime geometry |
| `CRTBranch` | Runtime scene branch |
| `CRTDummy` | Runtime dummy |
| `CRTSocket` | Runtime socket (attachment point) |

### Character Visuals

| Class | Purpose |
|-------|---------|
| `CCompChar` | Compound character model |
| `CCompBldg` | Compound building model |
| `CCompSimple` | Simple compound model |
| `CCompoundObj` / `ICompoundObj` | Compound object interface |
| `CCharacterDependentData` | Character visual data |
| `CObjAvartar::CharacterVisualChange` | Avatar equipment visual |
| `CObjItem::CharacterVisualChange` | Item visual change |
| `CObjDefalutCloth::CharacterVisualChange` | Cloth visual |
| `CObjSkill::CharacterVisualChange` | Skill visual change |

### Navigation

| Class | Purpose |
|-------|---------|
| `CRTNavMesh` | Runtime navigation mesh (base) |
| `CRTNavMeshTerrain` | Terrain nav mesh |
| `CRTNavMeshObj` | Object nav mesh |
| `CRTNavMeshDungeon` | Dungeon nav mesh |
| `CRTNavCell` | Nav cell (base) |
| `CRTNavCellTri` | Triangle nav cell |
| `CRTNavCellQuad` | Quad nav cell |
| `CRTNavEdge` | Nav edge (base) |
| `CRTNavEdgeGlobal` | Global nav edge |
| `CRTNavEdgeInternal` | Internal nav edge |
| `CNavCell` | Nav cell (builder) |
| `CNavMeshBuilder` | Nav mesh builder |

## Effect System

| Class | Purpose |
|-------|---------|
| `CEFSystem` | Effect system core |
| `CEFEffect` | Effect instance |
| `CEFElement` | Effect element |
| `CEFGroup` | Effect group |
| `CEFStoredEffect` | Stored effect template |
| `CEFStoredObject` | Stored effect object |
| `CEFController` | Effect controller |
| `CEFUpdater` | Effect updater |
| `CEFMesh` | Effect mesh |
| `CEFRenderSystem` | Effect renderer |
| `CEFGlobal` | Effect global data |
| `CGlobalEffectManager` | Global effect manager |
| `CEffectParticle` | Particle effect |

## Weather System

| Class | Purpose |
|-------|---------|
| `CWeather` | Weather base |
| `CGWeatherManager` | Weather manager |
| `CWRain` | Rain effect |
| `CWRainWave` | Rain wave effect |
| `CWRainWaveSplash` | Rain splash |
| `CWSnow` / `CWSnow2` | Snow effect |

## File System

| Class | Purpose |
|-------|---------|
| `CFileSystem` | File system abstraction |
| `CFileLegacy` | Legacy file access |
| `CFileMM` | Memory-mapped file |
| `CFileMem` | In-memory file |
| `IFile` | File interface |
| `CAutoFileManager` | Auto file manager |
| `CResourceMgr` / `IResourceMgr` | Resource manager |
| `CResIDManager` | Resource ID manager |
| `CDDJD3D` | DDJ to D3D texture loader |
| `CDDJFile` | DDJ file reader |
| `CDDJMem` | DDJ in-memory reader |
| `CTga` / `CTaga` | TGA image reader |
| `CJArchiveFm` | JoyMax archive (file mode) |
| `CJArchiveMem` | JoyMax archive (memory mode) |

## Application Core

| Class | Purpose |
|-------|---------|
| `CGame` | Main game class |
| `CGWorld` | Game world |
| `CGObj` | Game object |
| `CSystem` | System utilities |
| `CSysInfo` | System information |
| `CIntro` | Intro sequence |
| `CPSilkroad` | Main application |
| `CPSTitle` | Title screen |
| `CPSLogo` | Logo screen |
| `CPSCharacterSelect` | Character select screen |
| `CPSCharacterCreateChina` | Chinese character creation |
| `CPSCharacterCreateEurope` | European character creation |
| `CPSMission` | Mission/gameplay state |
| `CPSQuit` | Quit state |
| `CPSRestart` | Restart state |
| `CPSVersionCheck` | Version check state |
| `CPSQuickStart` | Quick start |

## Scripting

| Class | Purpose |
|-------|---------|
| `CEScript` | Script engine |
| `CGScript` | Game script |
| `CScriptCommandBase` | Script command base |
| `CEEProgram` / `CEEProgramBase` | Script program |
| `CEESource` / `CEESourceList` | Script source |
| `CEEOneCommand` | Single script command |
| `CEEStaticCommand` | Static script command |
| `CEEStaticProgram` | Static script program |
| `CEEObject` | Script object |
| `CEERefObject` | Script reference object |
| `CEEGlobalData` | Script global data |

### Script Commands (SC_*)

Prefixed `SC_` classes are individual script commands used in cutscenes and events:

| Class | Purpose |
|-------|---------|
| `SC_Start` / `SC_End` | Script start/end markers |
| `SC_ObjectCreate` | Create object in scene |
| `SC_ObjectRelease` | Remove object |
| `SC_ObjectMoveTo` | Move object |
| `SC_ObjectAniToName` | Play animation by name |
| `SC_CameraCreate` | Create camera |
| `SC_CameraTeleport` | Teleport camera |
| `SC_CameraShake` | Camera shake effect |
| `SC_EffectCreate` | Create visual effect |
| `SC_Fade` | Screen fade |
| `SC_ChatPlayer` | Player chat in cutscene |
| `SC_ChatNotice` | Notice text |
| `SC_SubTitle` | Subtitle display |
| `SC_SetBGM` | Set background music |
| `SC_SoundPlay` | Play sound effect |
| `SC_Teleport` | Teleport player |
| `SC_Ride` | Mount/dismount |
| `SC_Lighting` | Lighting change |
| `SC_SetWorldTime` | Set world time |
| `SC_DecoSkillTarget` | Skill targeting visual |

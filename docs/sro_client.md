# sro_client.exe - Main Game Client

## PE Structure

| Section | Virtual Size | Raw Size | Virtual Address |
|---------|-------------|----------|-----------------|
| .text | 0x0097E24A | 0x0097F000 | 0x00001000 |
| .rdata | 0x0012DD17 | 0x0012E000 | 0x00980000 |
| .data | 0x002B4C10 | 0x0003A000 | 0x00AAE000 |
| .rsrc | 0x0000B8C8 | 0x0000C000 | 0x00D63000 |

Total file size: ~11 MB. The .text section alone is ~9.9 MB, indicating a large codebase.

## Imported DLLs

**Core System**: KERNEL32.dll, USER32.dll, GDI32.dll, ADVAPI32.dll, SHELL32.dll, IMM32.dll, ole32.dll, VERSION.dll

**Graphics**: d3d9.dll (primary renderer), DDRAW.dll (fallback/legacy), d3d9d.dll (debug build reference)

**Audio**: DSOUND.dll (DirectSound), WINMM.dll (multimedia timers/audio)

**Network**: WS2_32.dll (Winsock 2 TCP/UDP), mswsock.dll (extended Winsock), WININET.dll (HTTP/FTP), iphlpapi.dll (IP helper), inetmib1.dll (SNMP MIB)

**Anti-Cheat**: XTrapVa.dll, XPva03.dll, psapi.dll

**File System**: GFXFileManager.dll (PK2 archive I/O)

**Plugin**: SRO_Plugin.dll, TestGame-d.dll (debug game plugin at `GIGame\TestGame-d.dll`)

**Debug**: dbghelp.dll (crash dump generation), mscoree.dll (.NET runtime, likely optional)

## Build Information

Source paths found in the binary:

```
D:\vss-od\Silkroad\Client\client\CharacterVisualChangeManager.cpp
D:\vss-od\Silkroad\Client\client\GScript.cpp
D:\vss-od\Silkroad\Client\client\ICATStruct.cpp
D:\vss-od\Silkroad\Client\client\IFConsole.cpp
D:\vss-od\Silkroad\Client\client\IFGNGWCRank.cpp
D:\vss-od\Silkroad\Client\client\IFRenderStatic.cpp
D:\vss-od\Silkroad\Client\client\IFSupporterChatWnd.cpp
D:\vss-od\Silkroad\Client\client\IFTargetWindowFortressStructure.cpp
D:\vss-od\Silkroad\Client\client\MemBufManager.cpp
D:\vss-od\Silkroad\Client\client\MsgStreamBuffer.h
D:\vss-od\Silkroad\Client\client\NIFAllianceGuild.cpp
D:\vss-od\Silkroad\Client\client\NIFBattleArenaGuildWnd.cpp
D:\vss-od\Silkroad\Client\client\NIFBattleArenaRuleWnd.cpp
D:\vss-od\Silkroad\Client\client\NIFEnchantWnd.cpp
D:\vss-od\Silkroad\Client\client\NIFGuildWnd.cpp
D:\vss-od\Silkroad\Client\client\NIFHostileGuild.cpp
D:\vss-od\Silkroad\Client\client\NIFOpenMarket.cpp
D:\vss-od\Silkroad\Client\client\NIFOpenMarketAlramWnd.cpp
D:\vss-od\Silkroad\Client\client\NIFOption.cpp
D:\vss-od\JMX_Library\EngineCommon\IMemory.h
```

Build uses Visual SourceSafe (`vss-od`) for version control. Two VSS roots are used:
- `D:\vss-od\` - Client source code
- `G:\VSS-OD\` - JMX shared libraries (GFXFileManager PDB: `g:\VSS-OD\JMX_Library\GFX\Out\Release\GFXFileManager\GFXFileManager.pdb`)

### Build Variant Identifiers

Strings in the binary reference multiple build configurations:
- `Silkroad_TestIn` - Internal test build (this client)
- `Silkroad_TestExt` - External test build
- `vtest` - Version test identifier

### Linker Info

- **Linker version**: 8.0 (MSVC 2005 / Visual Studio 2005)
- **Entry point RVA**: 0x00749B52
- **Image base**: 0x00400000
- **PE timestamp**: 0x4E311CB6

## Network Architecture

### Core Classes

| Class | Purpose |
|-------|---------|
| `CSession` | Session management, file transfer |
| `CSockStream` | Stream socket wrapper, file sending |
| `CBaseSocket` | Base socket abstraction |
| `CUdpPingClient` | UDP latency measurement (client) |
| `CUdpPingServer` | UDP latency measurement (server) |
| `CBlowFish` | Packet encryption/decryption |
| `PeerSessionContext` | Peer connection context |

### Server Architecture

The client connects through a two-stage server system:

1. **GatewayServer** - Initial connection point, authentication, server list
2. **AgentServer** - Game world server after authentication

### Known Server IPs

| IP | Likely Role |
|----|-------------|
| 211.115.86.66 | Korean server infrastructure (Joymax) |
| 121.14.13.139 | Chinese server infrastructure |

### Encryption

All network traffic uses **Blowfish** encryption via the `CBlowFish` class. The connection handshake includes:

- `_OnMsgReceivedBeforeHandshake()` - Initial handshake processing
- Server signature verification (checked in both client and launcher)
- Handshake failure codes logged with message IDs: `Handshake Failed:%d [MsgID: 0x%x]`
- Recipient info exchange during handshake

### Keep-Alive

```
cannot establish keep alive session : %d.%d.%d.%d %d (bind %d.%d.%d.%d)
```

The client maintains persistent keep-alive connections.

## Game Feature Classes

### Guild System
- `CGuildManager` - Core guild management
- `CIFGuildLevelUp`, `CIFGuildPointUp` - Guild progression
- `CIFGuildMasterElection` - Guild leader election
- `CIFGuildMasterLeave` - Guild leader departure
- `CIFGuildPositionGrant` - Rank assignment
- `CIFGuildSummonReq` - Guild summon
- `CIFGuildWar`, `CIFRequestGuildWar` - Guild warfare
- `CIFGuildNotifyContents`, `CIFGuildNotifyWrite` - Guild notices
- `CNIFAllianceGuild`, `CIFAllianceGuildSlot` - Guild alliances
- `CNIFHostileGuild`, `SHostileGuildInfo`, `SHostileGuildWar` - Hostile guild tracking

### Fortress/Siege System
- `CIFFortressBusiness`, `CIFFortressBusinessSlot` - Fortress commerce
- `CIFFortressMakeItemWnd` - Fortress item crafting
- `CIFFortressMap`, `CIFFortressMapFrame` - Fortress maps
- `CIFFortressWarApplyWnd` - Fortress war application
- `CIFTargetWindowFortressStructure` - Fortress structure targeting

### Enchantment
- `CIFAlchemyEnchantMagic` - Alchemy enchantment system
- `CNIFEnchantWnd` - Enchantment window

### Open Market
- `CIFOpenMarketAlramGuide` - Market alert/notification guide
- `CNIFOpenMarket` - Open market interface

### Skill/Mastery
- `CIFSkillMastery`, `CIFSkillMasteryWndManager` - Skill mastery UI
- `CMasteryData` - Mastery data management

### Battle Arena
- `CNIFBattleArenaGuildWnd` - Guild battle arena
- `CNIFBattleArenaRuleWnd` - Battle arena rules

## Internal File Path References

The client accesses assets through PK2 archives using path prefixes (`%s` = archive root):

### Text Data Files (`textdata\`)

Game logic and configuration tables loaded at runtime:

| File | Purpose |
|------|---------|
| characterdata.txt | Character definitions |
| charactervisualchange.txt | Character visual transformation data |
| itemdata.txt | Item definitions |
| item_grouping.txt | Item group/category data |
| itemeffect.txt | Item visual effects |
| skilldataenc.txt | Encrypted skill definitions |
| skilleffect.txt | Skill visual effects |
| skillgroup.txt | Skill groupings |
| skillmasterydata.txt | Mastery tree data |
| erasablemastery.txt | Removable mastery entries |
| erasableskill.txt | Removable skill entries |
| leveldata.txt | Level progression tables |
| levelgold.txt | Gold per level data |
| questdata.txt | Quest definitions |
| questcontentsdata.txt | Quest content |
| teleportdata.txt | Teleport locations |
| teleportlink.txt | Teleport connections |
| teleportbuilding.txt | Teleport building associations |
| npcpos.txt | NPC positions |
| npcchat.txt | NPC dialog |
| specialnpcdata.txt | Special NPC definitions |
| eventdata.txt | Event system data |
| eventguidedata.txt | Event guides |
| eventzonedata.txt | Event zone definitions |
| gameworldconfigdata.txt | World configuration |
| gameworlddata.txt | World definitions |
| abusefilter.txt | Chat profanity filter |
| magicoption.txt | Magic option definitions |
| magicoptionassign.txt | Magic option assignments |
| siegefortress.txt | Siege fortress data |
| siegefortressbattlerank.txt | Siege battle rankings |
| siegefortressitemforge.txt | Siege item forging |
| siegefortressreward.txt | Siege rewards |
| siegestructupgradedata.txt | Siege structure upgrades |
| gachaitemset.txt | Gacha/lottery items |
| gachanpcmap.txt | Gacha NPC locations |
| collectionbook_item.txt | Collection book items |
| collectionbook_theme.txt | Collection book themes |
| worldmap_mapinfo.txt | World map data |
| worldmap_localinfo.txt | Local map data |
| worldmap_instanceinfo.txt | Instance map data |

*(Plus ~30 more ref*.txt shop/trade/reward configuration files)*

### Config Files (`config\`)

| File | Purpose |
|------|---------|
| cameradata.txt | Camera parameters |
| command.txt | Command definitions |
| define.txt | Game constants/defines |
| option.txt | Client options |

### Other Asset Paths

- `event\event_npc_look.txt` - Event NPC appearance data
- `resinfo\` - Resource info files (e.g., `iftw_commonenemy.txt`)
- `interface\` - UI textures (.ddj, .bsr)
- `effect\` - Visual effect textures
- `icon\` - Icon assets
- `gateport.txt` - Gateway server port configuration (root level)
- `divisioninfo.txt` - Server division/region info
- `config\agreement.txt` - Terms of service / agreement text
- `event\unity_server.txt` - Event server configuration

### Settings Path

- `%s\Setting\Exception.dat` - Exception/crash log
- `%s\Setting\GNGWCRank.txt` - Guild war rank data
- `%s\Setting\srch.txt` - Search settings
- `%s\Setting\chop.dat` - Unknown game state data
- `%s\Setting\gmwp.dat` - Game world position data
- `%s\Setting\gmwpfort.dat` - Fortress world position data
- `%s\RallyPoint.txt` - Rally point data

## Asset Formats

| Extension | Description |
|-----------|-------------|
| .ddj | JoyMax compressed texture (DDS variant) |
| .dds | DirectDraw Surface texture |
| .bsr | JoyMax binary scene/model resource |
| .2dt | 2D terrain/tile data |
| .bmp | Bitmap images (guild marks: `guildmark.bmp`, `unionmark.bmp`) |
| .jpg | Screenshots: `SRO[YYYY-MM-DD HH-MM-SS]_NN.jpg` |

Resource format header: `JMXV` prefix (seen in multiple asset format checks).

## Debug/Logging

- **Exception handler**: `SetUnhandledExceptionFilter` / `UnhandledExceptionFilter`
- **Crash dumps**: `MiniDumpWriteDump` to `Dump\` directory
  - Dump filename format: `%s%d%c[%04d-%02d-%02d %02d-%02d-%02d]_%02d_%02d %s_%s.dmp`
  - Uploaded via `silkerrsender.exe` to `dmp.sro.joymax.com`
- **Exception log**: `%s\Setting\Exception.dat`
- **Screenshots**: `%s%s\SRO[%04d-%02d-%02d %02d-%02d-%02d]_%02d.jpg` (date-stamped JPEG)
- **Debug logging**: `[[Log_%d]]_%s.txt` format with numbered log files
- **Debug markers**: `jmxdebug._m_` (JoyMax debug flag)
- **Memory diagnostics**: "memory dump", "arg buff memory dump", "original memory dump" strings present

## Plugin System

- **SRO_Plugin.dll** - Referenced by name; likely loaded dynamically for extensibility
- **TestGame-d.dll** - Debug game plugin at path `GIGame\TestGame-d.dll`; the `-d` suffix indicates a debug build variant

## Registry Access

- `Software\Joymax\Silkroad` - Main application registry key (version info, settings)
- `SOFTWARE\Joymax\` - Parent key, used for mutex check: `"Critical Error!! Mutex already created!!"`

# Silkroad Online Client Architecture Overview

## Build Information

- **Build source path**: `D:\vss-od\Silkroad\Client\client\`
- **Engine library path**: `D:\vss-od\JMX_Library\EngineCommon\`
- **Build type**: Test/Development build (`Silkroad_TestIn`)
- **Registry key**: `HKCU\Software\Joymax\Silkroad`

## Component Flow

```
silkroad.exe (Launcher)
  |
  +--> Version check / patch detection (GATEPORT.TXT, reflinkurl.txt)
  +--> Download updates via DownloadServer
  +--> Launch sro_client.exe
         |
         +--> GFXFileManager.dll (PK2 archive I/O)
         +--> XTrapVa.dll / XTrap subsystem (anti-cheat)
         +--> Connect to GatewayServer -> AgentServer
         +--> Game session
  |
  replacer.exe (Updater)
  |   Applies downloaded patches, verifies Media.pk2 integrity
  |
  silkerrsender.exe (Crash Reporter)
      Sends .dmp crash dumps via FTP
```

## Directory Structure

```
Silkroad_TestIn/
|-- sro_client.exe          11 MB     Main game client
|-- silkroad.exe            760 KB    Launcher UI
|-- replacer.exe            320 KB    Updater/patcher
|-- silkerrsender.exe       252 KB    Crash dump sender
|-- GFXFileManager.dll      448 KB    PK2 archive manager
|-- XPva03.dll              96 KB     UPX-packed XTrap library
|-- Silkroad.ico            2.2 KB    Application icon
|-- silkcfg.dat             23 B      Core client config
|-- Silkload.dat            170 B     Hex-encoded encrypted loader config
|-- xtrap.dat               168 B     Hex-encoded XTrap config
|
|-- Data.pk2                2.0 GB    Game data archive (items, skills, textures, UI)
|-- Map.pk2                 886 MB    World map/terrain data
|-- Media.pk2               602 MB    Media assets (models, animations)
|-- Particles.pk2           77 MB     Particle effects
|-- Music.pk2               59 MB     Music/audio files
|
|-- setting/
|   |-- SROptionSet.dat     681 B     Graphics/sound/UI settings
|   |-- wndpos.dat          96 B      Window positions/dimensions
|   |-- SRChattingBlockingList.dat  8 B   Chat block list (empty)
|   |-- SRExtQSOption.dat   10 B      Quick-slot option flags
|
|-- XTrap/
|   |-- XTrapVa.dll         833 KB    Anti-cheat detection engine
|   |-- XTrap.xt            897 KB    Anti-cheat protection module (PE32)
|   |-- XTrapExt.dll        44 KB     Anti-cheat extension hooks
|   |-- psapi.dll           22.5 KB   Process enumeration API
|   |-- XDataFI0.Xtp        308 B     Encrypted XTrap config
|
|-- Dump/                              Crash dump output directory
|-- temppath/                          Temporary file storage
|   |-- Copia de DNINF.dat  1.6 MB    (copied data file)
```

## PK2 Archives Summary

All `.pk2` files use the "JoyMax File Manager!" format with Blowfish encryption. Total archive size: ~3.66 GB.

| Archive | Size | Contents |
|---------|------|----------|
| Data.pk2 | 2.0 GB | Game data: items, skills, characters, textures, UI, text data |
| Map.pk2 | 886 MB | World terrain, navigation meshes, region data |
| Media.pk2 | 602 MB | 3D models, animations, visual assets |
| Particles.pk2 | 77 MB | Particle effect definitions and textures |
| Music.pk2 | 59 MB | Background music, ambient audio |

## Key DLL Dependencies

| DLL | Purpose |
|-----|---------|
| GFXFileManager.dll | PK2 archive reading/writing (Blowfish encrypted) |
| d3d9.dll / DDRAW.dll | DirectX 9 rendering |
| DSOUND.dll / WINMM.dll | Audio output |
| WS2_32.dll | Winsock 2 networking |
| WININET.dll | HTTP/FTP for updates |
| XTrapVa.dll | Anti-cheat detection |
| dbghelp.dll | Crash dump generation (MiniDumpWriteDump) |
| psapi.dll | Process enumeration (anti-cheat) |

## Related Documentation

- [Main Game Client](sro_client.md)
- [PK2 Archive Format](pk2_format.md)
- [Launcher & Patcher](launcher_and_patcher.md)
- [Anti-Cheat System](anticheat.md)
- [Configuration Files](config_files.md)
- [Network Protocol](network_protocol.md)

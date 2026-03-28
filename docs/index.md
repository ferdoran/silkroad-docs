# Silkroad Online Client Documentation

Reverse-engineered documentation of the **Silkroad Online** game client (`Silkroad_TestIn`), a development/test build compiled from `D:\vss-od\Silkroad\Client\client\`.

## Contents

### Architecture
- [Overview](overview.md) - High-level component architecture and data flow
- [Client Binary](sro_client.md) - Binary analysis: RTTI classes, vtables, key functions
- [Anti-Cheat](anticheat.md) - Anti-cheat and integrity checking mechanisms
- [Config Files](config_files.md) - Configuration file formats and registry keys
- [Launcher & Patcher](launcher_and_patcher.md) - Launcher flow and patching system

### File Formats
- [PK2 Archive](pk2_format.md) - PK2 archive format (Blowfish-encrypted package files)
- [Asset Formats](asset_formats.md) - All JMXV-family asset formats (BMS, DDJ, BSR, NVM, BAN, BMT, BSK, CPD, DOF, MFO, IFO) and standard formats (DDS, WAV, TGA, TTF)

### Rendering
- [Character Rendering](character_rendering.md) - Character model composition, skeleton, and animation pipeline
- [Terrain Rendering](terrain_rendering.md) - Terrain tile system, LOD, and navigation mesh integration

### Network Protocol
- [Protocol Overview](network_protocol.md) - Packet framing, encryption, dispatch architecture, opcode tables
- [Server Binary Analysis](server_binary_analysis.md) - Server-side RE: dispatch table, corrected opcodes, full packet structures, IGObj API, DB schema
- [Message Index](messages/INDEX.md) - Complete index of all 289 documented message opcodes
- Individual message structure files with field-level detail for 268+ opcodes

### Game Systems
- [Item Structure](systems/item_structure.md) - Shared binary structure for inventory items (Rentable, Equipment, CoS, Etc)
- [Alchemy](systems/alchemy.md) - Alchemy system
- [COS / Pets](systems/cos_pet.md) - Companion system (pets, horses, transports)
- [Fortress Siege](systems/fortress_siege.md) - Fortress siege mechanics
- [Guild](systems/guild.md) - Guild system
- [Job / Trade](systems/job_trade.md) - Trade job system

## Quick Stats

| Category | Count |
|----------|-------|
| Documented opcodes | 289 |
| Opcodes with extracted fields | 268+ |
| Server → Client messages | ~130 |
| Client → Server messages | ~130 |
| JMXV asset format variants | 12 |
| RTTI classes identified | 50+ |

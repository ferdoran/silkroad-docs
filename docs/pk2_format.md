# PK2 Archive Format

## Table of Contents

- [Overview](#overview)
- [Header Structure](#header-structure)
- [Encryption](#encryption)
  - [Blowfish Block Encryption](#blowfish-block-encryption)
  - [Encryption Key](#encryption-key)
- [File List](#file-list)
- [Internal Structure](#internal-structure)
  - [Directory Entry Format](#directory-entry-format)
  - [Data.pk2 Directory Listing](#datapk2-directory-listing)
  - [Asset Types Inside PK2 Archives](#asset-types-inside-pk2-archives)
  - [Resource Format Version](#resource-format-version)
- [GFXFileManager.dll Classes](#gfxfilemanagerdll-classes)
  - [Magic Strings in DLL](#magic-strings-in-dll)
  - [Build Info](#build-info)
- [ECB Mode Implications](#ecb-mode-implications)

## Overview

PK2 is JoyMax's proprietary archive format used to package all game assets. It is managed by `GFXFileManager.dll` and uses Blowfish block encryption.

## Header Structure

The PK2 header is **256 bytes** (0x100):

```
Offset  Size  Description
0x00    21    Magic string: "JoyMax File Manager!" (null-terminated)
0x15    3     Padding (zeros)
0x18    8     Header metadata (version/flags)
                Byte 0x1E: 0x02 (format version or type indicator)
                Byte 0x20: 0x01, 0x01 (flags)
                Bytes 0x21-0x24: Varies per file (possibly creation timestamp or checksum)
0x25    219   Zero padding to offset 0x100
```

### Header Hex Dump (Data.pk2)

```
00000000: 4a6f 794d 6178 2046 696c 6520 4d61 6e61  JoyMax File Mana
00000010: 6765 7221 0a00 0000 0000 0000 0000 0200  ger!............
00000020: 0001 01d8 da30 0000 0000 0000 0000 0000  .....0..........
00000030-000000FF: All zeros (padding)
```

The magic string `"JoyMax File Manager!"` (20 bytes + newline `0x0A` + null) is consistent across all PK2 files.

## Encryption

### Blowfish Block Encryption

Starting at offset **0x100**, all data is encrypted with Blowfish in ECB mode using 8-byte blocks.

The first encrypted block across **all 5 PK2 files** decrypts to the same directory entry structure, producing the repeating ciphertext pattern:

```
Offset 0x100: b4c2 b953 09f0 0b01   (first 8-byte encrypted block)
Offset 0x108: 5f0a 39be a2f0 6a2f   (repeating pattern - encrypted zero/padding blocks)
```

The pattern `5f0a 39be a2f0 6a2f` repeats for many subsequent blocks, indicating these are **encrypted null/zero blocks**. This is characteristic of ECB mode where identical plaintext blocks produce identical ciphertext.

### Encryption Key

The Blowfish key is derived inside `GFXFileManager.dll`. The game passes the ASCII string `"169841"` (6 bytes: `31 36 39 38 34 31`) to `CBlowFish::Initialize()`, which XORs each byte with a static table embedded in the DLL before performing Blowfish key expansion.

**XOR table** (at DLL file offset `0x43228`):

```
03 f8 e4 44 88 99
```

**Key derivation:**

```
Base key:       31 36 39 38 34 31   ("169841")
XOR table:      03 f8 e4 44 88 99
                ─────────────────
Processed key:  32 ce dd 7c bc a8
```

The final 6-byte Blowfish key is `32 ce dd 7c bc a8`.

**LE Blowfish byte ordering:**

SRO's `CBlowFish` implementation reads and writes 8-byte blocks as two **little-endian** `u32` values, unlike the standard big-endian Blowfish specification. To decrypt with a standard (big-endian) Blowfish library:

```
1. Read 8-byte ciphertext block
2. Interpret as two LE u32 values: xL, xR
3. Swap to BE order: pack as BE u32 pair
4. Decrypt with standard Blowfish (key = 32 ce dd 7c bc a8)
5. Read result as two BE u32 values: pL, pR
6. Write back as two LE u32 values
```

```python
def decrypt_block_sro(bf, ct_block):
    """Decrypt one 8-byte block using SRO's LE Blowfish convention."""
    xL = struct.unpack('<I', ct_block[0:4])[0]
    xR = struct.unpack('<I', ct_block[4:8])[0]
    swapped = struct.pack('>II', xL, xR)
    plain_swapped = bf.decrypt(swapped)
    pL, pR = struct.unpack('>II', plain_swapped)
    return struct.pack('<II', pL, pR)
```

**Verification:** decrypting the first block at offset `0x100` across all 5 PK2 files produces valid directory entries (entry type byte followed by a null-terminated filename).

## File List

| Archive | Size | Description |
|---------|------|-------------|
| Data.pk2 | 2,037.6 MB | Primary game data (items, skills, textures, text tables, UI) |
| Map.pk2 | 886.0 MB | World terrain, navigation, region data |
| Media.pk2 | 602.0 MB | 3D models, animations, media assets |
| Particles.pk2 | 77.4 MB | Particle system definitions and textures |
| Music.pk2 | 59.3 MB | Background music, ambient sounds |

**Total**: ~3.66 GB

## Internal Structure

### Directory Entry Format

After decryption, PK2 files contain a hierarchical directory structure. Each entry includes:

- Entry type (file, directory, or end-of-directory marker)
- Filename (null-terminated string)
- File offset within the archive
- File size
- Timestamp data

### Data.pk2 Directory Listing

Data.pk2 contains a plaintext directory listing near the end of the file, which can be used to enumerate contents without full decryption.

### Asset Types Inside PK2 Archives

| Extension | Format | Description |
|-----------|--------|-------------|
| .ddj | JMXVDDJ | DDS texture wrapper (31,073 files) |
| .dds | DirectDraw Surface | Standard texture format (18,902 files) |
| .bms | JMXVBMS | Binary mesh geometry (16,852 files) |
| .bsr | JMXVRES | Binary scene resource (5,563 files) |
| .nvm | JMXVNVM | Navigation mesh (5,040 files) |
| .ban | JMXVBAN | Binary animation (3,564 files) |
| .bmt | JMXVBMT | Binary material (3,133 files) |
| .wav | RIFF WAVE | Sound effects (2,159 files) |
| .bsk | JMXVBSK | Binary skeleton (810 files) |
| .txt | Text | Tab-separated data tables (437 files) |
| .cpd | JMXVCPD | Character parameter data (70 files) |
| .dat | Various | AI nav data / BMP images (71 files) |
| .2dt | UI Template | UI widget definitions (42 files) |
| .dof | JMXVDOF | Dungeon object file (21 files) |
| .ifo | JMXVOBJI/2DTI | Object/tile index (4 files) |
| .mfo | JMXVMFO | Map info (1 file) |
| .c/.vsh/.psh | Text | Shader source code (60 files) |
| .tga | Targa | Image files (6 files) |
| .ttf | TrueType | Font files (3 files) |

For complete header structures and hex-level documentation of each format, see [Asset File Formats](asset_formats.md).

### Resource Format Version

All JoyMax-proprietary assets use the `JMXV` (JoyMax Version) 12-byte header prefix: 4 bytes magic `"JMXV"`, 4 bytes format ID (e.g., `"BMS "`, `"DDJ "`), and 4 bytes version string (e.g., `"0109"`, `"1000"`). The client performs multiple `JMXV` header checks when loading resources to validate format versions.

## GFXFileManager.dll Classes

| Class | Purpose |
|-------|---------|
| `CBlowFish` | Blowfish encryption/decryption for PK2 data |
| `CFMFile` | File abstraction for PK2 entries |
| `IFileManager` | Abstract file manager interface |
| `CPFileManager` | Physical (PK2) file manager implementation |
| `CWFileManager` | Write file manager (PK2 creation/modification) |
| `CAutoSavePath` | Auto-save path management (nested in CPFileManager) |

### Magic Strings in DLL

- `"JoyMax File Manager!"` - PK2 header magic
- `"Joymax Pak File"` - Internal format identifier

### Build Info

- **PDB path**: `g:\VSS-OD\JMX_Library\GFX\Out\Release\GFXFileManager\GFXFileManager.pdb`
- Built from the JMX shared library tree, separate from the game client source

## ECB Mode Implications

The use of ECB (Electronic Codebook) mode means:
1. Identical plaintext blocks always produce identical ciphertext blocks
2. The repeating `5f0a39bea2f06a2f` pattern reveals null/padding blocks
3. Block boundaries are visible in the encrypted data
4. No IV (Initialization Vector) is used

This is a known weakness but sufficient for asset protection against casual extraction.

## See Also

- [Asset File Formats](asset_formats.md) - Complete reference for all file formats inside PK2 archives
- [Character & Equipment Rendering](character_rendering.md) - How characters are assembled and rendered
- [Terrain & World Rendering](terrain_rendering.md) - Terrain geometry, texturing, shaders, and world structure
- [Network Protocol](network_protocol.md) - Network packet format, handshake, and encryption

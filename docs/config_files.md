# Configuration & Settings Files

## Root Directory Config Files

### silkcfg.dat (23 bytes)

Core client configuration. Binary format:

```
Offset  Hex                                       ASCII
0x00    0300 0000 0100 0000 0005 0000 0004 0000   ................
0x10    0000 0000 0001                             .......
```

Appears to contain a series of 32-bit little-endian integers:

| Offset | Value | Likely Purpose |
|--------|-------|----------------|
| 0x00 | 3 | Version or config format ID |
| 0x04 | 1 | Account or mode flag |
| 0x08 | 5 | Unknown setting (possibly locale: 5 = international?) |
| 0x0C | 4 | Unknown setting |
| 0x10 | 0 | Flag (disabled) |
| 0x14 | 0x0001 | Flag (enabled) |

> **Note**: Exact field meanings are uncertain without runtime analysis. Values may represent version number, locale ID, graphics mode, or account type flags.

### Silkload.dat (170 bytes)

Hex-encoded encrypted loader configuration. The entire file content is ASCII hex characters:

```
660970B4E849D93EE63C6D9849CFED62CBFA91FB2C16EABF
BFB6ACFCBB61A163A3200BB3E32873D8393323E3D4104B38
282A1FA80D51B4121660FCF8DFB2BCB40F7D04245246E456
F726430D8B1E255D3D35898F4B
```

Each pair of hex characters encodes one byte of the actual encrypted payload (170 hex chars = 85 bytes of encrypted data).

Shares its first 16 hex characters (`660970B4E849D93E`) with `xtrap.dat`, indicating a common encryption scheme or header format. See [Anti-Cheat documentation](anticheat.md) for comparison.

### xtrap.dat (168 bytes)

Hex-encoded encrypted XTrap configuration. Format identical to Silkload.dat:

```
660970B4E849D93EE33D6D9849CFE562
9377339C0F3B1A5EF952D0EC31DF0403
...
```

168 hex characters = 84 bytes of encrypted payload.

---

## Setting Directory (`setting/`)

### SROptionSet.dat (681 bytes)

Graphics, sound, and UI settings. Binary key-value format:

**Header** (4 bytes):
```
Offset  Value   Description
0x00    0x0D    Number of entries in first section (13)
0x02    0x2700  Unknown (possibly section size or checksum = 9984)
```

**Entry Format**:
Each entry appears to be:
```
[2-byte ID] [4-byte value]
```

Where the 2-byte ID contains a type flag in the high byte and a setting index in the low byte.

**Observed Entry Types**:

| ID Range | Type Flag | Likely Category |
|----------|-----------|-----------------|
| 0x00-0x0D | 0x00-0x01 | Graphics settings (resolution, quality, effects) |
| 0x0E-0x0F | 0x02-0x12 | Advanced graphics (shadows, textures) |
| 0xF5-0xF8 | 0x01 | Sound settings |
| 0x65-0x72 | 0x00-0x02 | UI settings |
| 0x59-0x5C | 0x00 | Additional settings |
| 0xE9-0xEE | 0x03 | Extended settings |
| 0xD1-0xD8 | 0x07 | UI layout/visibility |

**Notable Values**:
- Entry at ~0xD0: Contains `0x6F6F73` which decodes to ASCII `"oos"` - possibly a string value or marker
- Most values are 0 (disabled) or 1 (enabled), suggesting boolean toggles
- Some entries have larger values (0x1E = 30, 0x32 = 50) likely representing slider positions

### wndpos.dat (96 bytes)

Window positions and dimensions. Tracks the layout of UI windows:

**Header**:
```
Offset  Value  Description
0x00    3      Number of tracked windows
0x04    10     Unknown (possibly default padding or version)
```

**Window Entry Format** (appears to be ~28 bytes each):
```
[X position] [Y position] [Width] [Height] [Flags...]
```

**Window 1** (likely main/primary):
- Position: (800, 600) - `0x0320, 0x0258`
- Size: (332, 55) - `0x014C, 0x0037`

**Window 2**:
- Position: (80, 115) - `0x0050, 0x0073`
- Size: (80, 142) - `0x0050, 0x008E`

**Window 3**:
- Position: (218, 50) - `0x00DA, 0x0032`
- Size: (74, 30) - `0x004A, 0x001E`

Additional trailing data may represent minimized state, z-order, or visibility flags.

### SRChattingBlockingList.dat (8 bytes)

Chat block/ignore list.

```
0x00: 0100 0000 0000 0000
```

Structure:
- Bytes 0-3: Entry count = 1 (or version = 1)
- Bytes 4-7: Empty/zero (no blocked users)

This file is effectively empty - no users are blocked.

### SRExtQSOption.dat (10 bytes)

Quick-slot extension option flags.

```
0x00: 0100 0000 0101 0101 0000
```

Structure:
- Bytes 0-3: Version or count = 1
- Bytes 4-7: Four boolean flags, all enabled (0x01 each)
- Bytes 8-9: Two boolean flags, both disabled (0x00)

Likely controls which quick-slot bars are visible/active and their behavior options.

---

## Runtime-Created Files

### Exception.dat
**Path**: `%s\Setting\Exception.dat`

Created at runtime when crashes occur. Contains exception/crash information logged by the client's unhandled exception filter.

### GNGWCRank.txt
**Path**: `%s\Setting\GNGWCRank.txt`

Guild war ranking data, written during gameplay.

### srch.txt
**Path**: `%s\Setting\srch.txt`

Search history/settings, written during gameplay.

### Log Files
**Path**: `%s\[[Log_%d]]_%s.txt`

Numbered log files generated during client operation.

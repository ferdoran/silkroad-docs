# XTrap Anti-Cheat System

## Overview

Silkroad Online uses **XTrap** by WiseLogic as its anti-cheat protection system. The XTrap files are distributed across the root directory and `XTrap/` subdirectory.

## Component Files

### XTrapVa.dll (833 KB)
**Location**: `XTrap/XTrapVa.dll`
**Type**: PE32 DLL (GUI), Intel 80386

The main anti-cheat detection engine. Referenced directly by `sro_client.exe` as an import. Responsible for:
- Process and memory monitoring
- Debugger detection
- Code integrity verification
- Communication with XTrap server infrastructure

### XTrapExt.dll (44 KB)
**Location**: `XTrap/XTrapExt.dll`
**Type**: PE32 DLL (GUI), Intel 80386

Extension hooks library. Likely provides additional API hooking and system call interception for cheat detection.

### XTrap.xt (897 KB)
**Location**: `XTrap/XTrap.xt`
**Type**: PE32 executable (GUI), Intel 80386

Despite the `.xt` extension, this is a standard PE32 executable. Serves as the core anti-cheat protection module, possibly loaded and executed by XTrapVa.dll at runtime. Its larger size compared to XTrapVa.dll suggests it contains the bulk of the protection logic.

### XPva03.dll (96 KB)
**Location**: Root directory (`XPva03.dll`)
**Type**: PE32 DLL, **UPX-packed**

A packed XTrap support library. The UPX packing is identifiable by:
- Section names: `UPX0`, `UPX1`, `.rsrc`
- `UPX!` signature in the binary
- UPX version: 3.03

When unpacked, this likely provides additional detection or helper functions. Placed in the root directory (alongside `sro_client.exe`) for direct loading.

### psapi.dll (22.5 KB)
**Location**: `XTrap/psapi.dll`
**Type**: PE32 DLL (console), Intel 80386

A local copy of the Process Status API library. Normally a Windows system DLL, this local copy ensures:
1. Consistent API behavior across Windows versions
2. Prevention of system-level psapi.dll hooking/modification
3. Process enumeration for monitoring running processes

Used by XTrap to enumerate processes, detect known cheat tools, and monitor for suspicious process activity.

### XDataFI0.Xtp (308 bytes)
**Location**: `XTrap/XDataFI0.Xtp`

Encrypted configuration/data file. Contents are fully encrypted binary data (no plaintext markers). Likely contains:
- Detection signatures for known cheat tools
- Configuration parameters for the anti-cheat engine
- Update/versioning information

## Configuration Files

### xtrap.dat (168 bytes)
**Location**: Root directory

Hex-encoded encrypted configuration. The content is ASCII hex characters (0-9, A-F):

```
660970B4E849D93E E33D6D9849CFE562 9377339C0F3B1A5E ...
```

### Silkload.dat (170 bytes)
**Location**: Root directory

Hex-encoded encrypted loader configuration. Same encoding scheme as `xtrap.dat`:

```
660970B4E849D93E E63C6D9849CFED62 CBFA91FB2C16EABF ...
```

### Shared Prefix

Both `xtrap.dat` and `Silkload.dat` share the same **first 8 hex bytes**:

```
xtrap.dat:    660970B4E849D93E E33D6D9849CFE562 ...
Silkload.dat: 660970B4E849D93E E63C6D9849CFED62 ...
```

The shared prefix `660970B4E849D93E` (8 bytes = 16 hex chars) likely represents a common header, version identifier, or encryption initialization value. The data diverges starting at byte 9, where the actual configuration differs.

Both files also share a **common suffix** at offset 0x80:

```
0F7D04245246E456 F726430D8B1E...
```

This shared tail may be a checksum, signature, or common configuration block.

## Integration with Game Client

The game client (`sro_client.exe`) loads XTrap through:

1. **Direct import**: `XTrapVa.dll` and `XPva03.dll` are listed in the import table
2. **Runtime loading**: XTrap.xt and other components loaded dynamically
3. **Process monitoring**: psapi.dll enables process enumeration

The XTrap system is initialized during client startup. The `'xtrap.txt' Is not existing.. Using` message in `sro_client.exe` suggests an optional XTrap text configuration file that falls back to defaults when missing.

## Protection Mechanisms (Observed)

Based on the component analysis:

1. **Process scanning** - Enumerates running processes via psapi to detect known cheat tools
2. **Code packing** - XPva03.dll uses UPX to resist static analysis
3. **Binary protection** - XTrap.xt is a full PE executable loaded as a protection module
4. **Encrypted configuration** - XDataFI0.Xtp and hex-encoded .dat files prevent config tampering
5. **Integrity verification** - Multiple components cross-reference each other

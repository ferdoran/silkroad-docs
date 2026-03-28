# SERVER_ENTITY_SPAWN_INFO

> **Direction corrected** (server RE): The server **sends** this packet to the client;
> the "CLIENT_" prefix in the client-derived name reflects the client-side naming convention.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB155` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0087FE00` |
| Send site | `0x0050A013` (SR_GameServer.exe clean) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `SpawnType` | `u8` | 1 | Type of spawn event |
| 2 | `unk01` | `u8` | 1 | Sub-type or flags |
| 3 | `unk02` | `u8` | 1 | Additional flags |
| 4 | `UniqueID` | `u32` | 4 | Entity unique ID |
| 5 | `unk03` | `u8` | 1 | Entity state or spawn phase |
| 6 | `unk04` | `u8` | 1 | Additional info byte |

### Structure Summary

```
  [0] SpawnType                          u8
  [1] unk01                              u8
  [2] unk02                              u8
  [3] UniqueID                           u32
  [7] unk03                              u8
  [8] unk04                              u8
```

Total payload: **9 bytes**

### Binary Evidence

Disassembly of send sequence starting at VA `0x50A013` (SR_GameServer.exe clean).
Write sizes confirmed from `eax` register before each `call 0x404090`:

| Write VA | `eax` | Notes |
|----------|-------|-------|
| `0x0050A063` | 1 | SpawnType (BYTE) |
| `0x0050A074` | 1 | unk01 (BYTE) |
| `0x0050A085` | 1 | unk02 (BYTE) |
| `0x0050A096` | 4 | UniqueID (DWORD) |
| `0x0050A182` | 1 | unk03 (BYTE) |
| `0x0050A193` | 1 | unk04 (BYTE) |

Send: `mov edx, [eax + 0x27c]; push esi; call edx` at VA `0x0050A1A3`.

### String References

| String | Type |
|--------|------|
| `ITEM_QSP_ALL_POTION_1_01` | Debug — confirms inventory/spawn context |

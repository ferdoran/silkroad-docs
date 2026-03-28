# SERVER_GUILD_STORAGE_DATA

> **Corrected name** (server RE): Was `SERVER_ACADEMY_DATA_2` (client-derived). Binary analysis
> confirms this carries the **guild storage item buffer**.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3255` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088EB10` |
| Send mechanism | `fcn.00430a20(0xc66a00, session, 0x3255)` — massive-buffer send |
| Send site | `0x004E1D8C` (SR_GameServer.exe clean) |

### Fields

This packet is sent via the massive-buffer mechanism (`fcn.00430a20`) rather than the
standard field-by-field vtable path. The payload is the entire serialized content of the
guild storage, built into the global buffer `0xc66a00` by `fcn.004b8ad0`.

**One packet per guild storage page / batch of items.**

#### Per-Item Structure (inside buffer)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Slot` | `u8` | 1 | Storage slot index |
| 2 | `RentableType` | `u32` | 4 | Rental type (0 = normal) |
| 3 | `RefItemID` | `u32` | 4 | Item reference ID |
| 4 | `Quantity` | `u16` | 2 | Stack quantity |
| 5 | `Plus` | `u8` | 1 | Enhancement level |
| 6 | `Durability` | `u8` | 1 | Durability (%) |

For full item detail see [ItemData](../systems/item_structure.md).

### Protocol Context

| Packet | Role |
|--------|------|
| `0x3253` | Guild storage open (item count) |
| `0x3255` `SERVER_GUILD_STORAGE_DATA` | **Item data buffer (massive-buffer packet)** |
| `0x3254` `SERVER_GUILD_STORAGE_DATA_END` | End marker |

### Binary Evidence

Disassembly at VA `0x4E1D8C` — the opcode is pushed as the 3rd argument to the
massive-buffer sender:

```asm
004E1D8C: push 0x3255              ; opcode (arg3)
004E1D91: push esi                 ; session (arg2)
004E1D92: push 0xc66a00            ; buffer (arg1)
004E1DBB: call 0x430a20            ; SendMassiveMsg(buffer, session, opcode)
```

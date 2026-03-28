# SERVER_SIEGE_STATUS

> **Corrected name and direction** (server RE): Was `CLIENT_SIEGE_RESPONSE` (client-derived).
> The server **sends** this packet to notify clients of siege operation results.
> The binary contains multiple send-sites inside a large switch (31 siege states).
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB05E` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0087FE40` |
| Send sites | `0x006234FE`, `0x0062390F`, `0x0062398E` (SR_GameServer.exe clean) |

### Overview

This packet is sent by multiple siege operation handlers. The payload **varies by
siege operation state** (a 31-case switch on `siegeState`). Three distinct
field sequences have been identified from the binary:

---

### Variant A — Detailed siege status (send site `0x006234FE`)

Sent for the main siege result report.

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Result` | `u8` | 1 | Operation result code |
| 2 | `SiegeType` | `u8` | 1 | Siege type/category |
| 3 | `TaxAmount` | `u64` | 8 | Tax/gold amount (INT64) |
| 4 | `State1` | `u8` | 1 | Siege state flag 1 |
| 5 | `Data1` | `u32` | 4 | Data field 1 |
| 6 | `Data2` | `u32` | 4 | Data field 2 |
| 7 | `Flag1` | `u8` | 1 | Additional flag |
| 8 | `Flag2` | `u8` | 1 | Additional flag |
| 9 | `Info1` | `u16` | 2 | Info word 1 |
| 10 | `Flag3` | `u8` | 1 | Additional flag |
| 11 | `Flag4` | `u8` | 1 | Additional flag |
| 12 | `Info2` | `u16` | 2 | Info word 2 |
| 13 | `Flag5` | `u8` | 1 | Additional flag |
| 14 | `Flag6` | `u8` | 1 | Additional flag |
| 15 | `Info3` | `u16` | 2 | Info word 3 |

Total: **31 bytes**

---

### Variant B — Compact siege status (send site `0x0062390F`)

Sent after siege move/position update.

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Result` | `u8` | 1 | Operation result |
| 2 | `SubType` | `u8` | 1 | Sub-operation type |
| 3 | `Data1` | `u16` | 2 | Data word 1 |
| 4 | `Flag1` | `u8` | 1 | Flag |
| 5 | `Flag2` | `u8` | 1 | Flag |
| 6 | `Flag3` | `u8` | 1 | Flag |
| 7 | `Flag4` | `u8` | 1 | Flag |
| 8 | `Data2` | `u16` | 2 | Data word 2 |
| 9 | `Data3` | `u16` | 2 | Data word 3 |
| 10 | `Data4` | `u16` | 2 | Data word 4 |
| 11 | `Data5` | `u16` | 2 | Data word 5 |
| 12 | `Data6` | `u16` | 2 | Data word 6 |
| 13 | `Data7` | `u16` | 2 | Data word 7 |
| 14 | `Data8` | `u16` | 2 | Data word 8 |
| 15 | `Flag5` | `u8` | 1 | Flag |
| 16 | `Flag6` | `u8` | 1 | Flag |

Total: **22 bytes**

---

### Variant C — Minimal siege status (send site `0x0062398E`)

Sent for simple siege acknowledge.

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Result` | `u8` | 1 | Operation result |
| 2 | `SubType` | `u8` | 1 | Sub-operation type |
| 3 | `Flag1` | `u8` | 1 | Flag |
| 4 | `Flag2` | `u8` | 1 | Flag |
| 5 | `Data1` | `u16` | 2 | Data word 1 |
| 6 | `Data2` | `u16` | 2 | Data word 2 |
| 7 | `Data3` | `u16` | 2 | Data word 3 |
| 8 | `Data4` | `u16` | 2 | Data word 4 |
| 9 | `Data5` | `u16` | 2 | Data word 5 |
| 10 | `Data6` | `u16` | 2 | Data word 6 |
| 11 | `Data7` | `u16` | 2 | Data word 7 |
| 12 | `Flag3` | `u8` | 1 | Flag |
| 13 | `Flag4` | `u8` | 1 | Flag |

Total: **18 bytes**

### Binary Evidence

All variants confirmed from `eax`-tracked `call 0x404090` sequences within
`fcn.006232c0` (SR_GameServer.exe clean), which handles all 31 siege operation states.

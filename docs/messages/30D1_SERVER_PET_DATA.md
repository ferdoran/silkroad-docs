# SERVER_PET_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30D1` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4980` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwPetRefID` | `u32` | 4 | `0x00A56731` |
| 2 | `dwOwnerUID` | `u32` | 4 | `0x00A5673F` |
| 3 | `wHappiness` | `u16` | 2 | `0x00A5674D` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] dwPetRefID                     u32
  [   4] dwOwnerUID                     u32
  [   8] wHappiness                     u16
```

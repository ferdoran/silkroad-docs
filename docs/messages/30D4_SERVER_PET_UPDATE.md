# SERVER_PET_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x30D4` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7D20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUpdateType` | `u8` | 1 | `0x008A7D31` |
| 2 | `dwPetUID` | `u32` | 4 | `0x008A7D4C` |
| 3 | `byParam` | `u8` | 1 | `0x008A7D5A` |
| 4 | `dwValue` | `u32` | 4 | `0x008A7D68` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byUpdateType                   u8
  [   1] dwPetUID                       u32
  [   5] byParam                        u8
  [   6] dwValue                        u32
```

# SERVER_NPC_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0x30BF` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6640` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x009A19AA` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x009A19B8` |
| 3 | `dwResponseType` | `u32` | 4 | `0x009A1AB6` |
| 4 | `dwParam` | `u32` | 4 | `0x009A1AC4` |
| 5 | `ullData` | `u64` | 8 | `0x009A1ADA` |
| 6 | `byNPCType` | `u8` | 1 | `0x009A1AE8` |
| 7 | `wDialogID` | `u16` | 2 | `0x009A1AF6` |
| 8 | `dwPriceRate` | `u32` | 4 | `0x009A1B69` |
| 9 | `byCanTrade` | `u8` | 1 | `0x009A1BB2` |
| 10 | `byCanStore` | `u8` | 1 | `0x009A1CB3` |
| 11 | `byCanRepair` | `u8` | 1 | `0x009A1CCE` |
| 12 | `dwGold` | `u32` | 4 | `0x009A1D12` |
| 13 | `bySpecialFlag` | `u8` | 1 | `0x009A1D41` |

**Total size**: 39 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwUniqueID                     u32
  [   8] dwResponseType                 u32
  [  12] dwParam                        u32
  [  16] ullData                        u64
  [  24] byNPCType                      u8
  [  25] wDialogID                      u16
  [  27] dwPriceRate                    u32
  [  31] byCanTrade                     u8
  [  32] byCanStore                     u8
  [  33] byCanRepair                    u8
  [  34] dwGold                         u32
  [  38] bySpecialFlag                  u8
```

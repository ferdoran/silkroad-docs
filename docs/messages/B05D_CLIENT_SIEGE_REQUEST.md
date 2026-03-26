# CLIENT_SIEGE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB05D` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00895BB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x00895BFB` |
| 2 | `bySubType` | `u8` | 1 | `0x00895C25` |
| 3 | `dwGuildID` | `u32` | 4 | `0x00895CCE` |
| 4 | `dwParam1` | `u16` | 2 | `0x004F7A7D` |
| 5 | `dwParam2` | `bytes` | variable | `0x004F7AB9` |
| 6 | `dwParam3` | `u32` | 4 | `0x00895CEE` |
| 7 | `dwParam4` | `u32` | 4 | `0x00895D1D` |
| 8 | `byFlags` | `u32` | 4 | `0x00895D2E` |
| 9 | `dwTargetID` | `u32` | 4 | `0x00895D3F` |
| 10 | `byConfirm` | `u8` | 1 | `0x00895D4D` |
| 11 | `dwValue` | `u32` | 4 | `0x00895D8B` |
| 12 | `byExtra` | `u8` | 1 | `0x00895D99` |
| 13 | `dwExtraParam` | `u32` | 4 | `0x00895DAE` |
| 14 | `byField_14` | `u8` | 1 | `0x00895EA3` |
| 15 | `dwField_15` | `u32` | 4 | `0x00895EC2` |

**Minimum size**: 39 bytes + variable fields

### Structure Summary

```
  [   0] byType                         u8
  [   1] bySubType                      u8
  [   2] dwGuildID                      u32
  [   6] dwParam1                       u16
  [   8] dwParam2                       bytes  (variable length)
  [   0] dwParam3                       u32
  [   4] dwParam4                       u32
  [   8] byFlags                        u32
  [  12] dwTargetID                     u32
  [  16] byConfirm                      u8
  [  17] dwValue                        u32
  [  21] byExtra                        u8
  [  22] dwExtraParam                   u32
  [  26] byField_14                     u8
  [  27] dwField_15                     u32
```

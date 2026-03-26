# CLIENT_RANKING_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB507` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x008A38A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A38EB` |
| 2 | `byField_02` | `u8` | 1 | `0x008A3912` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A397C` |
| 4 | `byField_04` | `u8` | 1 | `0x008A398A` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A3998` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A39A6` |
| 7 | `ullField_07` | `u64` | 8 | `0x008A39B4` |
| 8 | `ullField_08` | `u64` | 8 | `0x008A39C2` |
| 9 | `ullField_09` | `u64` | 8 | `0x008A39D0` |
| 10 | `dwField_10` | `u32` | 4 | `0x008A39DE` |
| 11 | `wField_11` | `u16` | 2 | `0x008A3FBF` |

**Total size**: 45 bytes


### String References
| String | Type |
|--------|------|
| `ERROR - pOpenMarketRegistrationWnd != NULL` | Debug |
| `UIIT_STT_OPEN_MARKET_SELL` | UI |
| `UIIT_STT_OPEN_MARKET_DELETE_WARNING` | UI |
| `UIIT_STT_OPEN_MARKET_SELL_TIME_OVER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] dwField_05                     u32
  [  11] dwField_06                     u32
  [  15] ullField_07                    u64
  [  23] ullField_08                    u64
  [  31] ullField_09                    u64
  [  39] dwField_10                     u32
  [  43] wField_11                      u16
```

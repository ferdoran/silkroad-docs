# CLIENT_GUILD_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB30A` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x008820B0`, `0x00886310` |

## Handler 1: `0x008820B0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008820BE` |
| 2 | `wParam` | `u16` | 2 | `0x008820F5` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

## Handler 2: `0x00886310`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0088635A` |
| 2 | `wParam` | `u32` | 4 | `0x008863A1` |
| 3 | `byType` | `u16` | 2 | `0x004F7A7D` |
| 4 | `dwMemberUID1` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwMemberUID2` | `u32` | 4 | `0x008863BB` |
| 6 | `dwFriendUID` | `u32` | 4 | `0x0088645A` |
| 7 | `dwParam` | `u32` | 4 | `0x00886499` |
| 8 | `byOnlineFlag` | `u8` | 1 | `0x008864A7` |
| 9 | `dwExtraUID` | `u32` | 4 | `0x00886667` |
| 10 | `dwAssocUID` | `u32` | 4 | `0x00886675` |
| 11 | `byResult` | `u8` | 1 | `0x00886710` |

**Minimum size**: 29 bytes + variable fields

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u32
  [   5] byType                         u16
  [   7] dwMemberUID1                   bytes  (variable length)
  [   0] dwMemberUID2                   u32
  [   4] dwFriendUID                    u32
  [   8] dwParam                        u32
  [  12] byOnlineFlag                   u8
  [  13] dwExtraUID                     u32
  [  17] dwAssocUID                     u32
  [  21] byResult                       u8
```

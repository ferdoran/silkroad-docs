# SERVER_NOTICE

| Property | Value |
|----------|-------|
| Opcode | `0x3100` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088A420` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwNoticeType` | `u32` | 4 | `0x0088A46A` |
| 2 | `bytesTitle` | `bytes` | variable | `0x0088A48E` |
| 3 | `wBodyLen` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesBody` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwDuration` | `u32` | 4 | `0x0088A51F` |
| 6 | `dwTimestamp` | `u32` | 4 | `0x0088A52D` |
| 7 | `dwParam` | `u32` | 4 | `0x0088A53B` |
| 8 | `byPriority` | `u8` | 1 | `0x0088A549` |
| 9 | `byChannel` | `u8` | 1 | `0x0088A563` |

**Minimum size**: 20 bytes + variable fields

### Structure Summary

```
  [   0] dwNoticeType                   u32
  [   4] bytesTitle                     bytes  (variable length)
  [   0] wBodyLen                       u16
  [   2] bytesBody                      bytes  (variable length)
  [   0] dwDuration                     u32
  [   4] dwTimestamp                    u32
  [   8] dwParam                        u32
  [  12] byPriority                     u8
  [  13] byChannel                      u8
```

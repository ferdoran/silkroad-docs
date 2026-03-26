# CLIENT_COS_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB110` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00885920` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u16` | 2 | `0x004F7A7D` |
| 2 | `dwGuildWarID` | `bytes` | variable | `0x004F7AB9` |
| 3 | `bySubType` | `u8` | 1 | `0x008859A6` |
| 4 | `dwTargetGuildID` | `u32` | 4 | `0x008859B4` |
| 5 | `byField_05` | `u8` | 1 | `0x008859C2` |
| 6 | `dwField_06` | `u32` | 4 | `0x008859D0` |

**Minimum size**: 12 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `overlapped_job_id` | Debug |
| `sender_jid` | Debug |

### Structure Summary

```
  [   0] byType                         u16
  [   2] dwGuildWarID                   bytes  (variable length)
  [   0] bySubType                      u8
  [   1] dwTargetGuildID                u32
  [   5] byField_05                     u8
  [   6] dwField_06                     u32
```

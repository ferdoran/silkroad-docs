# SERVER_ENTITY_DAMAGE

| Property | Value |
|----------|-------|
| Opcode | `0x3068` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0087A7B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byDamageType` | `u8` | 1 | `0x0087A7FB` |
| 2 | `byAttackType` | `u8` | 1 | `0x0087A833` |
| 3 | `wDamage` | `u16` | 2 | `0x0087A841` |
| 4 | `wAbsorbed` | `u16` | 2 | `0x0087A84F` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byDamageType                   u8
  [   1] byAttackType                   u8
  [   2] wDamage                        u16
  [   4] wAbsorbed                      u16
```

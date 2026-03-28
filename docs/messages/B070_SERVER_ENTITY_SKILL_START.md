# SERVER_ENTITY_SKILL_START

> **Corrected name** (server RE): Was `CLIENT_ENTITY_POSITION_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB070` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A52F0` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Success` | `bool` | 1 | Whether the skill cast succeeded |

If `Success`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `CastType` | `u8` | 1 | 0=Buff, 2=Attack |
| 3 | `unkByte01` | `u8` | 1 | Skill execution flag? |
| 4 | `SkillID` | `u32` | 4 | Skill reference ID |
| 5 | `SourceUniqueID` | `u32` | 4 | Casting entity |
| 6 | `SkillUniqueID` | `u32` | 4 | Unique instance ID for this skill cast |
| 7 | `TargetUniqueID` | `u32` | 4 | Target entity |

If `CastType == 2` (Attack): followed by [DamageData](#damagedata-shared-sub-structure).

### DamageData (shared sub-structure)

```
bool    HasDamage
if HasDamage:
    u8      HitCount
    u8      TargetCount            // AOE targets
    for each target:
        u32     TargetUniqueID
        u8      DamageEffect       // flags: 1=KnockBack, 2=Block, 4=Position, 8=Cancel, 128=Dead
        if DamageEffect == 128: (target died — no further fields)
        elif (Block|Cancel): skip damage fields
        u8      DamageType         // flags: 1=Normal, 2=Critical, 4=Status
        u32     DamageValue
        u8      unkByte01          // possibly absorbed damage
        u8      unkByte02          // possibly reflected damage flag
        u8      unkByte03          // possibly status effect ID
```

### Structure Summary

```
  [   0] Success                        bool
  if Success:
    [   1] CastType                     u8        // 0=Buff, 2=Attack
    [   2] unkByte01                    u8
    [   3] SkillID                      u32
    [   7] SourceUniqueID               u32
    [  11] SkillUniqueID                u32
    [  15] TargetUniqueID               u32
    if CastType == 2:
      [  19] DamageData                 (variable)
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A52FF` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A530D` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

# SERVER_MASTERY_SKILL_LEVELDOWN_RESPONSE

> Previously documented as `CLIENT_SKILL_DATA` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB202` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x00880E90` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `newSkillID` | `u32` | 4 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880E9F` |
| 2 | `dwMasteryID` | `u32` | 4 | `0x00880EB9` |
| 3 | `byAction` | `u8` | 1 | `0x00880EC7` |

**Total size**: 6 bytes

</details>
### Source File(s)
- `NetProcessInInterface.cpp`

### Assert Expressions
```
m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)
```

### String References
| String | Type |
|--------|------|
| `m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwMasteryID                    u32
  [   5] byAction                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct SkillData {
        uint8_t byResult;
        uint32_t dwMasteryID;
        uint8_t byAction;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record SkillData(
        byte byResult,
        uint dwMasteryID,
        byte byAction
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct SkillData {
        pub by_result: u8,
        pub dw_mastery_id: u32,
        pub by_action: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type SkillData struct {
        byResult uint8
        dwMasteryID uint32
        byAction uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface SkillData {
        byResult: number;
        dwMasteryID: number;
        byAction: number;
    }
    ```


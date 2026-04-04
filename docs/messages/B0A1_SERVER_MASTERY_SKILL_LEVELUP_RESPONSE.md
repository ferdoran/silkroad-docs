# SERVER_MASTERY_SKILL_LEVELUP_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SKILL_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0A1` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A5360` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byAction` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `newSkillID` | `u32` | 4 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A5374` |
| 2 | `dwSkillID` | `u32` | 4 | `0x008A53A0` |
| 3 | `dwTargetUID` | `u32` | 4 | `0x008A53AE` |

**Total size**: 9 bytes

</details>
### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwSkillID                      u32
  [   5] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MasterySkillLevelupResponse {
        uint8_t byAction;
        uint32_t dwSkillID;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MasterySkillLevelupResponse(
        byte byAction,
        uint dwSkillID,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MasterySkillLevelupResponse {
        pub by_action: u8,
        pub dw_skill_id: u32,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type MasterySkillLevelupResponse struct {
        byAction uint8
        dwSkillID uint32
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MasterySkillLevelupResponse {
        byAction: number;
        dwSkillID: number;
        dwTargetUID: number;
    }
    ```


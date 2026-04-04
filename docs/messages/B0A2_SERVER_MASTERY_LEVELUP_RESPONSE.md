# SERVER_MASTERY_LEVELUP_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SKILL_USE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0A2` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880BE0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `masteryID` | `u32` | 4 | if(packet.ReadBool() |
| 3 | `Level` | `u8` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880BEE` |
| 2 | `dwSkillID` | `u32` | 4 | `0x00880C08` |

**Total size**: 5 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwSkillID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MasteryLevelupResponse {
        uint8_t byResult;
        uint32_t dwSkillID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MasteryLevelupResponse(
        byte byResult,
        uint dwSkillID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MasteryLevelupResponse {
        pub by_result: u8,
        pub dw_skill_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type MasteryLevelupResponse struct {
        byResult uint8
        dwSkillID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MasteryLevelupResponse {
        byResult: number;
        dwSkillID: number;
    }
    ```


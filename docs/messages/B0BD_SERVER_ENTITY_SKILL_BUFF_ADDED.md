# SERVER_ENTITY_SKILL_BUFF_ADDED

> **Corrected name** (server RE): Was `CLIENT_STORAGE_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0BD` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4960` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `TargetUniqueID` | `u32` | 4 | Entity receiving the buff |
| 2 | `SkillID` | `u32` | 4 | Buff skill reference ID |
| 3 | `BuffUniqueID` | `u32` | 4 | Unique instance ID for this buff |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] TargetUniqueID                 u32
  [   4] SkillID                        u32
  [   8] BuffUniqueID                   u32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00A56691` |
| 2 | `wField_02` | `u16` | 2 | `0x00A566A8` |
| 3 | `dwField_03` | `u32` | 4 | `0x00A566B6` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySkillBuffAdded {
        uint32_t TargetUniqueID;
        uint32_t SkillID;
        uint32_t BuffUniqueID;
        uint8_t byResult;
        uint16_t wField_02;
        uint32_t dwField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySkillBuffAdded(
        uint TargetUniqueID,
        uint SkillID,
        uint BuffUniqueID,
        byte byResult,
        ushort wField_02,
        uint dwField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySkillBuffAdded {
        pub target_unique_id: u32,
        pub skill_id: u32,
        pub buff_unique_id: u32,
        pub by_result: u8,
        pub w_field_02: u16,
        pub dw_field_03: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySkillBuffAdded struct {
        TargetUniqueID uint32
        SkillID uint32
        BuffUniqueID uint32
        byResult uint8
        wField_02 uint16
        dwField_03 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySkillBuffAdded {
        targetUniqueID: number;
        skillID: number;
        buffUniqueID: number;
        byResult: number;
        wField_02: number;
        dwField_03: number;
    }
    ```


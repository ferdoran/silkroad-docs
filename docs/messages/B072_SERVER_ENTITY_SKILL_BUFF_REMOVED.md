# SERVER_ENTITY_SKILL_BUFF_REMOVED

> **Corrected name** (server RE): Was `CLIENT_ENTITY_STATUS_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB072` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4B00` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Success` | `bool` | 1 | Whether the buff was successfully removed |
| 2 | `BuffUniqueID` | `u32` | 4 | Unique instance ID of the removed buff (only if Success) |

**Minimum size**: 1 byte (failure), 5 bytes (success)

### Structure Summary

```
  [   0] Success                        bool
  if Success:
    [   1] BuffUniqueID                 u32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x008A4B11` |
| 2 | `dwParam1` | `u32` | 4 | `0x008A4B3A` |
| 3 | `bySubType` | `u8` | 1 | `0x008A4B48` |
| 4 | `dwUniqueID` | `u32` | 4 | `0x008A4B56` |
| 5 | `byFlags` | `u8` | 1 | `0x008A4B64` |
| 6 | `bytesPosition` | `bytes[3]` | 3 | `0x008A4B9D` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySkillBuffRemoved {
        bool Success;
        uint32_t BuffUniqueID;  // conditional
        uint8_t byType;
        uint32_t dwParam1;
        uint8_t bySubType;
        uint32_t dwUniqueID;
        uint8_t byFlags;
        uint8_t bytesPosition;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySkillBuffRemoved(
        bool Success,
        uint BuffUniqueID /* conditional */,
        byte byType,
        uint dwParam1,
        byte bySubType,
        uint dwUniqueID,
        byte byFlags,
        byte bytesPosition
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySkillBuffRemoved {
        pub success: bool,
        pub buff_unique_id: u32,  // conditional
        pub by_type: u8,
        pub dw_param1: u32,
        pub by_sub_type: u8,
        pub dw_unique_id: u32,
        pub by_flags: u8,
        pub bytes_position: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySkillBuffRemoved struct {
        Success bool
        BuffUniqueID uint32  // conditional
        byType uint8
        dwParam1 uint32
        bySubType uint8
        dwUniqueID uint32
        byFlags uint8
        bytesPosition uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySkillBuffRemoved {
        success: boolean;
        buffUniqueID: number;  // conditional
        byType: number;
        dwParam1: number;
        bySubType: number;
        dwUniqueID: number;
        byFlags: number;
        bytesPosition: number;
    }
    ```


# SERVER_PET_PLAYER_MOUNTED

> **Corrected name** (server RE): Was `CLIENT_QUEST_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB0CB` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A80A0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byAction` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `unk` | `u32` | 4 | if(packet.ReadBool() |
| 3 | `isMounting` | `bool` | 1 | if(packet.ReadBool() |
| 4 | `RidingUniqueID` | `u32` | 4 | if(packet.ReadBool() → if(isMounting) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A80B1` |
| 2 | `byAction` | `u8` | 1 | `0x008A80BF` |
| 3 | `byQuestType` | `u8` | 1 | `0x008A80CD` |

**Total size**: 6 bytes

</details>
### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] byQuestType                    u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetPlayerMounted {
        uint32_t dwUniqueID;
        uint8_t byAction;
        uint8_t byQuestType;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetPlayerMounted(
        uint dwUniqueID,
        byte byAction,
        byte byQuestType
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetPlayerMounted {
        pub dw_unique_id: u32,
        pub by_action: u8,
        pub by_quest_type: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetPlayerMounted struct {
        dwUniqueID uint32
        byAction uint8
        byQuestType uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetPlayerMounted {
        dwUniqueID: number;
        byAction: number;
        byQuestType: number;
    }
    ```


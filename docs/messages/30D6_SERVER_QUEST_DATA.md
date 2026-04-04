# SERVER_QUEST_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30D6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008743A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byQuestAction` | `u8` | 1 | `0x008743DE` |
| 2 | `wQuestCount` | `u16` | 2 | `0x008743F8` |
| 3 | `wQuestIDLen` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesQuestIDs` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwParam1` | `u32` | 4 | `0x008744AD` |
| 6 | `dwParam2` | `u32` | 4 | `0x008744BB` |
| 7 | `dwParam3` | `u32` | 4 | `0x008744C9` |
| 8 | `wObjective1` | `u16` | 2 | `0x00874616` |
| 9 | `wObjective2` | `u16` | 2 | `0x00874681` |
| 10 | `wObjective3` | `u16` | 2 | `0x00874746` |

**Minimum size**: 23 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `%s -> *%s` | Debug |
| `SiegeManager MSG Result - Fail.` | Debug |
| `Trigger Action MSG Result - Fail.` | Debug |
| `Player:%d, NPC_Mob:%d, DroppedItem:%d` | Debug |
| `-> %s` | Debug |
| `SiegeManager MSG Result - Ok.` | Debug |
| `UIIT_STT_COSNEWUI_TITLE` | UI |

### Structure Summary

```
  [   0] byQuestAction                  u8
  [   1] wQuestCount                    u16
  [   3] wQuestIDLen                    u16
  [   5] bytesQuestIDs                  bytes  (variable length)
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
  [   8] dwParam3                       u32
  [  12] wObjective1                    u16
  [  14] wObjective2                    u16
  [  16] wObjective3                    u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct QuestData {
        uint8_t byQuestAction;
        uint16_t wQuestCount;
        uint16_t wQuestIDLen;
        std::vector<uint8_t> bytesQuestIDs;
        uint32_t dwParam1;
        uint32_t dwParam2;
        uint32_t dwParam3;
        uint16_t wObjective1;
        uint16_t wObjective2;
        uint16_t wObjective3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record QuestData(
        byte byQuestAction,
        ushort wQuestCount,
        ushort wQuestIDLen,
        byte[] bytesQuestIDs,
        uint dwParam1,
        uint dwParam2,
        uint dwParam3,
        ushort wObjective1,
        ushort wObjective2,
        ushort wObjective3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct QuestData {
        pub by_quest_action: u8,
        pub w_quest_count: u16,
        pub w_quest_idlen: u16,
        pub bytes_quest_ids: Vec<u8>,
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub dw_param3: u32,
        pub w_objective1: u16,
        pub w_objective2: u16,
        pub w_objective3: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type QuestData struct {
        byQuestAction uint8
        wQuestCount uint16
        wQuestIDLen uint16
        bytesQuestIDs []byte
        dwParam1 uint32
        dwParam2 uint32
        dwParam3 uint32
        wObjective1 uint16
        wObjective2 uint16
        wObjective3 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface QuestData {
        byQuestAction: number;
        wQuestCount: number;
        wQuestIDLen: number;
        bytesQuestIDs: Uint8Array;
        dwParam1: number;
        dwParam2: number;
        dwParam3: number;
        wObjective1: number;
        wObjective2: number;
        wObjective3: number;
    }
    ```


# SERVER_QUEST_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30D7` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008811E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesQuestData` | `bytes` | variable | `0x00881208` |
| 2 | `byQuestType` | `u8` | 1 | `0x00881216` |
| 3 | `byQuestFlag` | `u8` | 1 | `0x00881224` |
| 4 | `wQuestID` | `u16` | 2 | `0x00881232` |
| 5 | `bytesRewardData` | `bytes[12]` | 12 | `0x00881240` |
| 6 | `dwQuestRefID` | `u32` | 4 | `0x00881255` |

**Minimum size**: 20 bytes + variable fields

### Structure Summary

```
  [   0] bytesQuestData                 bytes  (variable length)
  [   0] byQuestType                    u8
  [   1] byQuestFlag                    u8
  [   2] wQuestID                       u16
  [   4] bytesRewardData                bytes[12]
  [  16] dwQuestRefID                   u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct QuestUpdate {
        std::vector<uint8_t> bytesQuestData;
        uint8_t byQuestType;
        uint8_t byQuestFlag;
        uint16_t wQuestID;
        uint8_t bytesRewardData;
        uint32_t dwQuestRefID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record QuestUpdate(
        byte[] bytesQuestData,
        byte byQuestType,
        byte byQuestFlag,
        ushort wQuestID,
        byte bytesRewardData,
        uint dwQuestRefID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct QuestUpdate {
        pub bytes_quest_data: Vec<u8>,
        pub by_quest_type: u8,
        pub by_quest_flag: u8,
        pub w_quest_id: u16,
        pub bytes_reward_data: u8,
        pub dw_quest_ref_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type QuestUpdate struct {
        bytesQuestData []byte
        byQuestType uint8
        byQuestFlag uint8
        wQuestID uint16
        bytesRewardData uint8
        dwQuestRefID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface QuestUpdate {
        bytesQuestData: Uint8Array;
        byQuestType: number;
        byQuestFlag: number;
        wQuestID: number;
        bytesRewardData: number;
        dwQuestRefID: number;
    }
    ```


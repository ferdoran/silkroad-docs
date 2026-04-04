# SERVER_ENTITY_LEVEL_UP

> **Corrected name** (server RE): Was `SERVER_CHAT_MESSAGE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3054` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00889D90` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `uniqueID` | `u32` | 4 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byChatType` | `u8` | 1 | `0x00889DFD` |
| 2 | `wSenderLen` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesSender` | `bytes` | variable | `0x004F7AB9` |
| 4 | `byFlag` | `u8` | 1 | `0x00889E80` |
| 5 | `dwParam` | `u32` | 4 | `0x00889FAD` |

**Minimum size**: 8 bytes + variable fields

</details>
### Structure Summary

```
  [   0] byChatType                     u8
  [   1] wSenderLen                     u16
  [   3] bytesSender                    bytes  (variable length)
  [   0] byFlag                         u8
  [   1] dwParam                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityLevelUp {
        uint8_t byChatType;
        uint16_t wSenderLen;
        std::vector<uint8_t> bytesSender;
        uint8_t byFlag;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityLevelUp(
        byte byChatType,
        ushort wSenderLen,
        byte[] bytesSender,
        byte byFlag,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityLevelUp {
        pub by_chat_type: u8,
        pub w_sender_len: u16,
        pub bytes_sender: Vec<u8>,
        pub by_flag: u8,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityLevelUp struct {
        byChatType uint8
        wSenderLen uint16
        bytesSender []byte
        byFlag uint8
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityLevelUp {
        byChatType: number;
        wSenderLen: number;
        bytesSender: Uint8Array;
        byFlag: number;
        dwParam: number;
    }
    ```


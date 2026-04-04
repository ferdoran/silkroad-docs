# SERVER_GLOBAL_CHAT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3103` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088FD00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesMessage` | `bytes` | variable | `0x0088FD4F` |
| 2 | `dwParam1` | `u32` | 4 | `0x0088FD67` |
| 3 | `dwParam2` | `u32` | 4 | `0x0088FD75` |
| 4 | `bytesExtra` | `bytes` | variable | `0x0088FD82` |
| 5 | `wChannel` | `u16` | 2 | `0x00890174` |

**Minimum size**: 10 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_FORT_GUILD_COMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_SUBCOMMANDER` | UI |
| `UIIT_STT_FORT_GUILD_BATTLEMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_PRODUCTMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_TRAINERMANAGER` | UI |
| `UIIT_STT_FORT_GUILD_ENGINEER` | UI |
| `UIIT_MSG_FORT_POSITION_REMOVE_COMPLETE` | UI |
| `UIIT_MSG_FORT_POSITION_GRANT_COMPLETE` | UI |
| `UIIT_STT_CONFIRM_BOX` | UI |

### Structure Summary

```
  [   0] bytesMessage                   bytes  (variable length)
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
  [   8] bytesExtra                     bytes  (variable length)
  [   0] wChannel                       u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GlobalChat {
        std::vector<uint8_t> bytesMessage;
        uint32_t dwParam1;
        uint32_t dwParam2;
        std::vector<uint8_t> bytesExtra;
        uint16_t wChannel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GlobalChat(
        byte[] bytesMessage,
        uint dwParam1,
        uint dwParam2,
        byte[] bytesExtra,
        ushort wChannel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GlobalChat {
        pub bytes_message: Vec<u8>,
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub bytes_extra: Vec<u8>,
        pub w_channel: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type GlobalChat struct {
        bytesMessage []byte
        dwParam1 uint32
        dwParam2 uint32
        bytesExtra []byte
        wChannel uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GlobalChat {
        bytesMessage: Uint8Array;
        dwParam1: number;
        dwParam2: number;
        bytesExtra: Uint8Array;
        wChannel: number;
    }
    ```


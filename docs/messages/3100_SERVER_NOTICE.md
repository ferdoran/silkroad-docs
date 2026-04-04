# SERVER_NOTICE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3100` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x0088A420` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwNoticeType` | `u32` | 4 | `0x0088A46A` |
| 2 | `bytesTitle` | `bytes` | variable | `0x0088A48E` |
| 3 | `wBodyLen` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesBody` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwDuration` | `u32` | 4 | `0x0088A51F` |
| 6 | `dwTimestamp` | `u32` | 4 | `0x0088A52D` |
| 7 | `dwParam` | `u32` | 4 | `0x0088A53B` |
| 8 | `byPriority` | `u8` | 1 | `0x0088A549` |
| 9 | `byChannel` | `u8` | 1 | `0x0088A563` |

**Minimum size**: 20 bytes + variable fields

### Structure Summary

```
  [   0] dwNoticeType                   u32
  [   4] bytesTitle                     bytes  (variable length)
  [   0] wBodyLen                       u16
  [   2] bytesBody                      bytes  (variable length)
  [   0] dwDuration                     u32
  [   4] dwTimestamp                    u32
  [   8] dwParam                        u32
  [  12] byPriority                     u8
  [  13] byChannel                      u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct Notice {
        uint32_t dwNoticeType;
        std::vector<uint8_t> bytesTitle;
        uint16_t wBodyLen;
        std::vector<uint8_t> bytesBody;
        uint32_t dwDuration;
        uint32_t dwTimestamp;
        uint32_t dwParam;
        uint8_t byPriority;
        uint8_t byChannel;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record Notice(
        uint dwNoticeType,
        byte[] bytesTitle,
        ushort wBodyLen,
        byte[] bytesBody,
        uint dwDuration,
        uint dwTimestamp,
        uint dwParam,
        byte byPriority,
        byte byChannel
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct Notice {
        pub dw_notice_type: u32,
        pub bytes_title: Vec<u8>,
        pub w_body_len: u16,
        pub bytes_body: Vec<u8>,
        pub dw_duration: u32,
        pub dw_timestamp: u32,
        pub dw_param: u32,
        pub by_priority: u8,
        pub by_channel: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type Notice struct {
        dwNoticeType uint32
        bytesTitle []byte
        wBodyLen uint16
        bytesBody []byte
        dwDuration uint32
        dwTimestamp uint32
        dwParam uint32
        byPriority uint8
        byChannel uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface Notice {
        dwNoticeType: number;
        bytesTitle: Uint8Array;
        wBodyLen: number;
        bytesBody: Uint8Array;
        dwDuration: number;
        dwTimestamp: number;
        dwParam: number;
        byPriority: number;
        byChannel: number;
    }
    ```


# SERVER_MAIL_SEND_RESPONSE

> Previously documented as `CLIENT_GUILD_UPDATE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB309` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x00886170` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008861AD` |
| 2 | `byAction` | `u8` | 1 | `0x008861F6` |
| 3 | `wParam` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `wField_05` | `u16` | 2 | `0x008862C9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] wParam                         u16
  [   4] bytesData_3                    bytes  (variable length)
  [   0] wField_05                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildUpdate {
        uint8_t byResult;
        uint8_t byAction;
        uint16_t wParam;
        std::vector<uint8_t> bytesData_3;
        uint16_t wField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildUpdate(
        byte byResult,
        byte byAction,
        ushort wParam,
        byte[] bytesData_3,
        ushort wField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildUpdate {
        pub by_result: u8,
        pub by_action: u8,
        pub w_param: u16,
        pub bytes_data_3: Vec<u8>,
        pub w_field_05: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildUpdate struct {
        byResult uint8
        byAction uint8
        wParam uint16
        bytesData_3 []byte
        wField_05 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildUpdate {
        byResult: number;
        byAction: number;
        wParam: number;
        bytesData_3: Uint8Array;
        wField_05: number;
    }
    ```


# CLIENT_GUILD_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB30B` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x00886000` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwGuildID` | `u32` | 4 | `0x0088605B` |
| 2 | `dwMemberUID` | `u32` | 4 | `0x00886069` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 10 bytes + variable fields

### Structure Summary

```
  [   0] dwGuildID                      u32
  [   4] dwMemberUID                    u32
  [   8] wField_03                      u16
  [  10] bytesData_3                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildData {
        uint32_t dwGuildID;
        uint32_t dwMemberUID;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildData(
        uint dwGuildID,
        uint dwMemberUID,
        ushort wField_03,
        byte[] bytesData_3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildData {
        pub dw_guild_id: u32,
        pub dw_member_uid: u32,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildData struct {
        dwGuildID uint32
        dwMemberUID uint32
        wField_03 uint16
        bytesData_3 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildData {
        dwGuildID: number;
        dwMemberUID: number;
        wField_03: number;
        bytesData_3: Uint8Array;
    }
    ```


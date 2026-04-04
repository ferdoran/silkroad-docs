# SERVER_TITLE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30E6` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008ABCC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wTitleLen` | `u16` | 2 | `0x004F7A7D` |
| 2 | `bytesTitleName` | `bytes` | variable | `0x004F7AB9` |
| 3 | `dwTitleID` | `u32` | 4 | `0x008ABD22` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] wTitleLen                      u16
  [   2] bytesTitleName                 bytes  (variable length)
  [   0] dwTitleID                      u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TitleData {
        uint16_t wTitleLen;
        std::vector<uint8_t> bytesTitleName;
        uint32_t dwTitleID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TitleData(
        ushort wTitleLen,
        byte[] bytesTitleName,
        uint dwTitleID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TitleData {
        pub w_title_len: u16,
        pub bytes_title_name: Vec<u8>,
        pub dw_title_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type TitleData struct {
        wTitleLen uint16
        bytesTitleName []byte
        dwTitleID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TitleData {
        wTitleLen: number;
        bytesTitleName: Uint8Array;
        dwTitleID: number;
    }
    ```


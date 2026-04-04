# SERVER_NOTICE_UPDATE

> Previously documented as `SERVER_PATCH_INFO` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x300C` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0086E100` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `type` | `u8` | 1 |  |
| 2 | `unkByte01` | `u8` | 1 | case(5) → if(w.Character_cbxMessageUniques.Checked) |
| 3 | `modelID` | `u32` | 4 | case(5) → if(w.Character_cbxMessageUniques.Checked) |
| 4 | `unkByte01` | `u8` | 1 | case(5) → if(w.Character_cbxMessageUniques.Checked) → if(w.Character_cbxMessageUniques.Checked) |
| 5 | `modelID` | `u32` | 4 | case(5) → if(w.Character_cbxMessageUniques.Checked) → if(w.Character_cbxMessageUniques.Checked) |
| 6 | `player` | `string` | var | case(5) → if(w.Character_cbxMessageUniques.Checked) → if(w.Character_cbxMessageUniques.Checked) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesPatchData` | `bytes` | variable | `0x008416B1` |
| 2 | `bytesUrl` | `bytes` | variable | `0x00841948` |
| 3 | `wVersion` | `u16` | 2 | `0x0086DABF` |

**Minimum size**: 2 bytes + variable fields

</details>
### Structure Summary

```
  [   0] bytesPatchData                 bytes  (variable length)
  [   0] bytesUrl                       bytes  (variable length)
  [   0] wVersion                       u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PatchInfo {
        std::vector<uint8_t> bytesPatchData;
        std::vector<uint8_t> bytesUrl;
        uint16_t wVersion;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PatchInfo(
        byte[] bytesPatchData,
        byte[] bytesUrl,
        ushort wVersion
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PatchInfo {
        pub bytes_patch_data: Vec<u8>,
        pub bytes_url: Vec<u8>,
        pub w_version: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type PatchInfo struct {
        bytesPatchData []byte
        bytesUrl []byte
        wVersion uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PatchInfo {
        bytesPatchData: Uint8Array;
        bytesUrl: Uint8Array;
        wVersion: number;
    }
    ```


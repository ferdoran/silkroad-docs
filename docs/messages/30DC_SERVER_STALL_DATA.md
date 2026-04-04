# SERVER_STALL_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30DC` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00884A30`, `0x00881570` |

## Handler 1: `0x00884A30`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wStallNameLen` | `u16` | 2 | `0x004F7A7D` |
| 2 | `bytesStallName` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 2 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `SN_TALK_COMMON_END` | Debug |
| `snd_quest_end` | Debug |

### Structure Summary

```
  [   0] wStallNameLen                  u16
  [   2] bytesStallName                 bytes  (variable length)
```

## Handler 2: `0x00881570`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wStallNameLen` | `u8` | 1 | `0x00881584` |
| 2 | `bytesStallName` | `u8` | 1 | `0x008815A3` |

**Total size**: 2 bytes

### String References
| String | Type |
|--------|------|
| `SN_TALK_COMMON_END` | Debug |
| `snd_quest_end` | Debug |

### Structure Summary

```
  [   0] wStallNameLen                  u8
  [   1] bytesStallName                 u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallData {
        uint16_t wStallNameLen;
        std::vector<uint8_t> bytesStallName;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallData(
        ushort wStallNameLen,
        byte[] bytesStallName
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallData {
        pub w_stall_name_len: u16,
        pub bytes_stall_name: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallData struct {
        wStallNameLen uint16
        bytesStallName []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallData {
        wStallNameLen: number;
        bytesStallName: Uint8Array;
    }
    ```


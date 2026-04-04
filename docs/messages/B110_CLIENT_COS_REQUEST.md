# CLIENT_COS_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB110` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00885920` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u16` | 2 | `0x004F7A7D` |
| 2 | `dwGuildWarID` | `bytes` | variable | `0x004F7AB9` |
| 3 | `bySubType` | `u8` | 1 | `0x008859A6` |
| 4 | `dwTargetGuildID` | `u32` | 4 | `0x008859B4` |
| 5 | `byField_05` | `u8` | 1 | `0x008859C2` |
| 6 | `dwField_06` | `u32` | 4 | `0x008859D0` |

**Minimum size**: 12 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `overlapped_job_id` | Debug |
| `sender_jid` | Debug |

### Structure Summary

```
  [   0] byType                         u16
  [   2] dwGuildWarID                   bytes  (variable length)
  [   0] bySubType                      u8
  [   1] dwTargetGuildID                u32
  [   5] byField_05                     u8
  [   6] dwField_06                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosRequest {
        uint16_t byType;
        std::vector<uint8_t> dwGuildWarID;
        uint8_t bySubType;
        uint32_t dwTargetGuildID;
        uint8_t byField_05;
        uint32_t dwField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosRequest(
        ushort byType,
        byte[] dwGuildWarID,
        byte bySubType,
        uint dwTargetGuildID,
        byte byField_05,
        uint dwField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosRequest {
        pub by_type: u16,
        pub dw_guild_war_id: Vec<u8>,
        pub by_sub_type: u8,
        pub dw_target_guild_id: u32,
        pub by_field_05: u8,
        pub dw_field_06: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosRequest struct {
        byType uint16
        dwGuildWarID []byte
        bySubType uint8
        dwTargetGuildID uint32
        byField_05 uint8
        dwField_06 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosRequest {
        byType: number;
        dwGuildWarID: Uint8Array;
        bySubType: number;
        dwTargetGuildID: number;
        byField_05: number;
        dwField_06: number;
    }
    ```


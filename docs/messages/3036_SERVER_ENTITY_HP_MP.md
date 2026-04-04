# SERVER_ENTITY_HP_MP
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3036` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A9560` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A9594` |
| 2 | `byUpdateType` | `u8` | 1 | `0x008A95A2` |
| 3 | `dwValue` | `u32` | 4 | `0x008A95B0` |

**Total size**: 9 bytes

### String References
| String | Type |
|--------|------|
| `ITEM_SETITEM_DEACTIVE` | Debug |
| `snd_setitem_deactive` | Debug |

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byUpdateType                   u8
  [   5] dwValue                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityHpMp {
        uint32_t dwUniqueID;
        uint8_t byUpdateType;
        uint32_t dwValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityHpMp(
        uint dwUniqueID,
        byte byUpdateType,
        uint dwValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityHpMp {
        pub dw_unique_id: u32,
        pub by_update_type: u8,
        pub dw_value: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityHpMp struct {
        dwUniqueID uint32
        byUpdateType uint8
        dwValue uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityHpMp {
        dwUniqueID: number;
        byUpdateType: number;
        dwValue: number;
    }
    ```


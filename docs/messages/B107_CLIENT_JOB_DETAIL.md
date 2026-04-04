# CLIENT_JOB_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB107` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x008897C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088980A` |
| 2 | `byUnknown` | `bytes` | variable | `0x0088983E` |
| 3 | `bySlotType` | `u8` | 1 | `0x0088984C` |
| 4 | `dwItemID` | `u32` | 4 | `0x0088985A` |
| 5 | `dwParam1` | `u32` | 4 | `0x008898CD` |
| 6 | `byHasExtra` | `u8` | 1 | `0x008898DB` |
| 7 | `dwMinLevel` | `u32` | 4 | `0x008898F9` |
| 8 | `byUnknown2` | `bytes` | variable | `0x00889AA9` |
| 9 | `bySlotType2` | `u8` | 1 | `0x00889AB7` |
| 10 | `byAction` | `u8` | 1 | `0x00889AC5` |
| 11 | `byConfirm` | `u8` | 1 | `0x00889AD3` |
| 12 | `dwParam2` | `u32` | 4 | `0x00889B52` |
| 13 | `dwParam3` | `u32` | 4 | `0x00889B60` |

**Minimum size**: 26 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_MRELEASE_BEELETED` | UI |
| `UIIT_MSG_MRELEASE_BROKEN` | UI |

### Structure Summary

```
  [   0] byType                         u8
  [   1] byUnknown                      bytes  (variable length)
  [   0] bySlotType                     u8
  [   1] dwItemID                       u32
  [   5] dwParam1                       u32
  [   9] byHasExtra                     u8
  [  10] dwMinLevel                     u32
  [  14] byUnknown2                     bytes  (variable length)
  [   0] bySlotType2                    u8
  [   1] byAction                       u8
  [   2] byConfirm                      u8
  [   3] dwParam2                       u32
  [   7] dwParam3                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobDetail {
        uint8_t byType;
        std::vector<uint8_t> byUnknown;
        uint8_t bySlotType;
        uint32_t dwItemID;
        uint32_t dwParam1;
        uint8_t byHasExtra;
        uint32_t dwMinLevel;
        std::vector<uint8_t> byUnknown2;
        uint8_t bySlotType2;
        uint8_t byAction;
        uint8_t byConfirm;
        uint32_t dwParam2;
        uint32_t dwParam3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobDetail(
        byte byType,
        byte[] byUnknown,
        byte bySlotType,
        uint dwItemID,
        uint dwParam1,
        byte byHasExtra,
        uint dwMinLevel,
        byte[] byUnknown2,
        byte bySlotType2,
        byte byAction,
        byte byConfirm,
        uint dwParam2,
        uint dwParam3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobDetail {
        pub by_type: u8,
        pub by_unknown: Vec<u8>,
        pub by_slot_type: u8,
        pub dw_item_id: u32,
        pub dw_param1: u32,
        pub by_has_extra: u8,
        pub dw_min_level: u32,
        pub by_unknown2: Vec<u8>,
        pub by_slot_type2: u8,
        pub by_action: u8,
        pub by_confirm: u8,
        pub dw_param2: u32,
        pub dw_param3: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobDetail struct {
        byType uint8
        byUnknown []byte
        bySlotType uint8
        dwItemID uint32
        dwParam1 uint32
        byHasExtra uint8
        dwMinLevel uint32
        byUnknown2 []byte
        bySlotType2 uint8
        byAction uint8
        byConfirm uint8
        dwParam2 uint32
        dwParam3 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobDetail {
        byType: number;
        byUnknown: Uint8Array;
        bySlotType: number;
        dwItemID: number;
        dwParam1: number;
        byHasExtra: number;
        dwMinLevel: number;
        byUnknown2: Uint8Array;
        bySlotType2: number;
        byAction: number;
        byConfirm: number;
        dwParam2: number;
        dwParam3: number;
    }
    ```


# CLIENT_ENTITY_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0ED` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088A820`, `0x008867A0` |

## Handler 1: `0x0088A820`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUnknown` | `bytes` | variable | `0x0088A864` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x0088A872` |
| 3 | `byAction` | `u8` | 1 | `0x0088A8BB` |
| 4 | `bySubAction` | `u8` | 1 | `0x0088A8C9` |
| 5 | `dwParam` | `u32` | 4 | `0x0088A8E0` |

**Minimum size**: 10 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_CHAR_SKIN_CHANGE_SUCCESS` | UI |

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_EVENT_END` | UI |

### Structure Summary

```
  [   0] byUnknown                      bytes  (variable length)
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] bySubAction                    u8
  [   6] dwParam                        u32
```

## Handler 2: `0x008867A0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUnknown` | `u32` | 4 | `0x008867FC` |
| 2 | `dwUniqueID` | `u8` | 1 | `0x0088680A` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_CHAR_SKIN_CHANGE_SUCCESS` | UI |

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_EVENT_END` | UI |

### Structure Summary

```
  [   0] byUnknown                      u32
  [   4] dwUniqueID                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityUpdate {
        std::vector<uint8_t> byUnknown;
        uint32_t dwUniqueID;
        uint8_t byAction;
        uint8_t bySubAction;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityUpdate(
        byte[] byUnknown,
        uint dwUniqueID,
        byte byAction,
        byte bySubAction,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityUpdate {
        pub by_unknown: Vec<u8>,
        pub dw_unique_id: u32,
        pub by_action: u8,
        pub by_sub_action: u8,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityUpdate struct {
        byUnknown []byte
        dwUniqueID uint32
        byAction uint8
        bySubAction uint8
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityUpdate {
        byUnknown: Uint8Array;
        dwUniqueID: number;
        byAction: number;
        bySubAction: number;
        dwParam: number;
    }
    ```


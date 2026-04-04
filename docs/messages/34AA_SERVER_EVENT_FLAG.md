# SERVER_EVENT_FLAG
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x34AA` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x008999B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x008999C2` |
| 2 | `byField_02` | `u8` | 1 | `0x008999D0` |
| 3 | `byField_03` | `u8` | 1 | `0x008999DE` |

**Total size**: 4 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_VIETNAM_MRSYSTEM_100` | UI |
| `UIIT_MSG_VIETNAM_MRSYSTEM_50` | UI |
| `UIIT_MSG_VIETNAM_MRSYSTEM_0` | UI |

### Structure Summary

```
  [   0] wParam                         u16
  [   2] byField_02                     u8
  [   3] byField_03                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EventFlag {
        uint16_t wParam;
        uint8_t byField_02;
        uint8_t byField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EventFlag(
        ushort wParam,
        byte byField_02,
        byte byField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EventFlag {
        pub w_param: u16,
        pub by_field_02: u8,
        pub by_field_03: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EventFlag struct {
        wParam uint16
        byField_02 uint8
        byField_03 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EventFlag {
        wParam: number;
        byField_02: number;
        byField_03: number;
    }
    ```


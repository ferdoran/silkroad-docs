# CLIENT_ITEM_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E6` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008830F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00883121` |
| 2 | `byAction` | `u8` | 1 | `0x0088313B` |
| 3 | `dwTargetUID` | `u32` | 4 | `0x00883149` |

**Total size**: 6 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_OUTCOM_COMPLETE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ItemRequest {
        uint8_t byResult;
        uint8_t byAction;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ItemRequest(
        byte byResult,
        byte byAction,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ItemRequest {
        pub by_result: u8,
        pub by_action: u8,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ItemRequest struct {
        byResult uint8
        byAction uint8
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ItemRequest {
        byResult: number;
        byAction: number;
        dwTargetUID: number;
    }
    ```


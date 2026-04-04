# CLIENT_FORTRESS_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB461` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088D910` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D91E` |
| 2 | `wParam` | `u16` | 2 | `0x0088D987` |
| 3 | `byAction` | `u8` | 1 | `0x0088D9CE` |
| 4 | `byConfirm` | `u8` | 1 | `0x0088D9E4` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `snd_window_close` | Debug |
| `GuildSummonReq` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wParam                         u16
  [   3] byAction                       u8
  [   4] byConfirm                      u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct FortressRequest {
        uint8_t byResult;
        uint16_t wParam;
        uint8_t byAction;
        uint8_t byConfirm;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressRequest(
        byte byResult,
        ushort wParam,
        byte byAction,
        byte byConfirm
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressRequest {
        pub by_result: u8,
        pub w_param: u16,
        pub by_action: u8,
        pub by_confirm: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressRequest struct {
        byResult uint8
        wParam uint16
        byAction uint8
        byConfirm uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressRequest {
        byResult: number;
        wParam: number;
        byAction: number;
        byConfirm: number;
    }
    ```


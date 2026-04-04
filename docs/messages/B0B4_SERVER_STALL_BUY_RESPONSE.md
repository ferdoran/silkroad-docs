# SERVER_STALL_BUY_RESPONSE

> Previously documented as `CLIENT_PARTY_RESPONSE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB0B4` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872450` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 |  |
| 2 | `slotStall` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087245F` |
| 2 | `wParam` | `u16` | 2 | `0x008724C6` |
| 3 | `byAction` | `u8` | 1 | `0x0087250E` |
| 4 | `byConfirm` | `u8` | 1 | `0x00872532` |

**Total size**: 5 bytes

</details>
### String References
| String | Type |
|--------|------|
| `IFStall` | Debug |

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
    struct PartyResponse {
        uint8_t byResult;
        uint16_t wParam;
        uint8_t byAction;
        uint8_t byConfirm;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyResponse(
        byte byResult,
        ushort wParam,
        byte byAction,
        byte byConfirm
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyResponse {
        pub by_result: u8,
        pub w_param: u16,
        pub by_action: u8,
        pub by_confirm: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyResponse struct {
        byResult uint8
        wParam uint16
        byAction uint8
        byConfirm uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyResponse {
        byResult: number;
        wParam: number;
        byAction: number;
        byConfirm: number;
    }
    ```


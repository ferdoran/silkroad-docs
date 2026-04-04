# CLIENT_JOB_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB106` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x008857B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008857DF` |
| 2 | `wErrorCode` | `u16` | 2 | `0x00885860` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_MRELEASE_VOTING` | UI |
| `UIIT_MSG_MRELEASEERR_NOTVOTETIME` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobUpdate {
        uint8_t byResult;
        uint16_t wErrorCode;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobUpdate(
        byte byResult,
        ushort wErrorCode
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobUpdate {
        pub by_result: u8,
        pub w_error_code: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobUpdate struct {
        byResult uint8
        wErrorCode uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobUpdate {
        byResult: number;
        wErrorCode: number;
    }
    ```


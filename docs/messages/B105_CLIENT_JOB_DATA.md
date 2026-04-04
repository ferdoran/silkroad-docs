# CLIENT_JOB_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB105` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00881CB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881CBE` |
| 2 | `wParam` | `u16` | 2 | `0x00881CD8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobData {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobData(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobData {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobData struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobData {
        byAction: number;
        wParam: number;
    }
    ```


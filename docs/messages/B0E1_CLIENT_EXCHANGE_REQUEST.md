# CLIENT_EXCHANGE_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E1` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00884DD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byJobType` | `u8` | 1 | `0x00884E1B` |
| 2 | `byAction` | `u8` | 1 | `0x00884E29` |
| 3 | `dwTargetUID` | `u32` | 4 | `0x00884E37` |

**Total size**: 6 bytes

### Source File(s)
- `NetProcessInInterface.cpp`

### Domain
character class, job/trade system

### Assert Expressions
```
g_pMyPlayerObj->GetJobType() == byJobType
```

### String References
| String | Type |
|--------|------|
| `g_pMyPlayerObj->GetJobType() == byJobType` | Debug |
| `MERCHANT` | Debug |
| `THIEF` | Debug |
| `HUNTER` | Debug |
| `UIIT_STT_JOB_EXP_%s_LOST` | UI |
| `UIIT_STT_JOB_EXP_%s_GET` | UI |
| `UIIT_STT_CLASS_%s_%d` | UI |
| `UIIT_STT_CLASS_EU_%s_%d` | UI |
| `UIIT_STT_JOB_LVUP_%s_CLASS` | UI |

### Structure Summary

```
  [   0] byJobType                      u8
  [   1] byAction                       u8
  [   2] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ExchangeRequest {
        uint8_t byJobType;
        uint8_t byAction;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ExchangeRequest(
        byte byJobType,
        byte byAction,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ExchangeRequest {
        pub by_job_type: u8,
        pub by_action: u8,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ExchangeRequest struct {
        byJobType uint8
        byAction uint8
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ExchangeRequest {
        byJobType: number;
        byAction: number;
        dwTargetUID: number;
    }
    ```


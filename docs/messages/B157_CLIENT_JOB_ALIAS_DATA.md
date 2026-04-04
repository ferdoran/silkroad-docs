# CLIENT_JOB_ALIAS_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB157` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00872810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00872820` |
| 2 | `byStage` | `u8` | 1 | `0x0087284F` |
| 3 | `byAction` | `u8` | 1 | `0x00872865` |
| 4 | `dwTargetUID` | `u32` | 4 | `0x00872873` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byStage                        u8
  [   2] byAction                       u8
  [   3] dwTargetUID                    u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobAliasData {
        uint8_t byResult;
        uint8_t byStage;
        uint8_t byAction;
        uint32_t dwTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobAliasData(
        byte byResult,
        byte byStage,
        byte byAction,
        uint dwTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobAliasData {
        pub by_result: u8,
        pub by_stage: u8,
        pub by_action: u8,
        pub dw_target_uid: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobAliasData struct {
        byResult uint8
        byStage uint8
        byAction uint8
        dwTargetUID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobAliasData {
        byResult: number;
        byStage: number;
        byAction: number;
        dwTargetUID: number;
    }
    ```


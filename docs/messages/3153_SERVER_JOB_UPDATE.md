# SERVER_JOB_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3153` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008825D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008825F5` |
| 2 | `byField_02` | `u8` | 1 | `0x00882603` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_STRIP_CANCEL` | UI |
| `UIIT_MGS_ERR_FRPVP_ON_CANCEL` | UI |
| `UIIT_MGS_ERR_FRPVP_CANCEL_CHANGE_TEAM` | UI |
| `UIIT_MGS_ERR_FRPVP_OFF_CANCEL` | UI |

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byField_02                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobUpdate {
        uint32_t dwRefObjID;
        uint8_t byField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobUpdate(
        uint dwRefObjID,
        byte byField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobUpdate {
        pub dw_ref_obj_id: u32,
        pub by_field_02: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobUpdate struct {
        dwRefObjID uint32
        byField_02 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobUpdate {
        dwRefObjID: number;
        byField_02: number;
    }
    ```


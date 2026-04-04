# SERVER_BATTLE_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3532` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089AFA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089AFBC` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089AFCA` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleInfo {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleInfo(
        uint dwRefObjID,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleInfo {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleInfo struct {
        dwRefObjID uint32
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleInfo {
        dwRefObjID: number;
        dwField_02: number;
    }
    ```


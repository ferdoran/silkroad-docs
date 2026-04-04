# SERVER_BATTLE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3530` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089AD90`, `0x0089AFA0` |

## Handler 1: `0x0089AD90`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AD9E` |
| 2 | `byField_02` | `u8` | 1 | `0x0089ADDC` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089ADF9` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
```

## Handler 2: `0x0089AFA0`

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
    struct BattleData {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint32_t dwRefObjID;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleData(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        uint dwRefObjID,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleData {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleData struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        dwRefObjID uint32
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleData {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        dwRefObjID: number;
        dwField_02: number;
    }
    ```


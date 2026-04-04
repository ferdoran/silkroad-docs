# SERVER_ENTITY_STAT_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x330F` |
| Direction | Server → Client |
| Group | Game Extended 3 |
| Handler(s) | `0x008A59E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008A5A31` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A5A3F` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A5A4D` |
| 4 | `byField_04` | `u8` | 1 | `0x008A5A74` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A5AA9` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A5AC3` |

**Total size**: 21 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_SKILL_EXECUTE` | UI |

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
  [  13] dwField_05                     u32
  [  17] dwField_06                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityStatUpdate {
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStatUpdate(
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStatUpdate {
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStatUpdate struct {
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStatUpdate {
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
    }
    ```


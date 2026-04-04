# SERVER_FORTRESS_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x34D2` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0089A250`, `0x0089A310` |

## Handler 1: `0x0089A250`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089A25E` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
```

## Handler 2: `0x0089A310`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A322` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A369` |
| 3 | `byField_03` | `u8` | 1 | `0x0089A377` |
| 4 | `byField_04` | `u8` | 1 | `0x0089A385` |
| 5 | `byField_05` | `u8` | 1 | `0x0089A393` |
| 6 | `byField_06` | `u8` | 1 | `0x0089A3A1` |
| 7 | `byField_07` | `u8` | 1 | `0x0089A3AF` |
| 8 | `byField_08` | `u8` | 1 | `0x0089A3BD` |
| 9 | `byField_09` | `u8` | 1 | `0x0089A3CB` |
| 10 | `byField_10` | `u8` | 1 | `0x0089A3D9` |
| 11 | `dwField_11` | `u32` | 4 | `0x0089A405` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089A413` |

**Total size**: 18 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] byField_05                     u8
  [   5] byField_06                     u8
  [   6] byField_07                     u8
  [   7] byField_08                     u8
  [   8] byField_09                     u8
  [   9] byField_10                     u8
  [  10] dwField_11                     u32
  [  14] dwField_12                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct FortressUpdate {
        uint32_t dwRefObjID;
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint8_t byField_04;
        uint8_t byField_05;
        uint8_t byField_06;
        uint8_t byField_07;
        uint8_t byField_08;
        uint8_t byField_09;
        uint8_t byField_10;
        uint32_t dwField_11;
        uint32_t dwField_12;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressUpdate(
        uint dwRefObjID,
        byte byResult,
        byte byField_02,
        byte byField_03,
        byte byField_04,
        byte byField_05,
        byte byField_06,
        byte byField_07,
        byte byField_08,
        byte byField_09,
        byte byField_10,
        uint dwField_11,
        uint dwField_12
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressUpdate {
        pub dw_ref_obj_id: u32,
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub by_field_05: u8,
        pub by_field_06: u8,
        pub by_field_07: u8,
        pub by_field_08: u8,
        pub by_field_09: u8,
        pub by_field_10: u8,
        pub dw_field_11: u32,
        pub dw_field_12: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressUpdate struct {
        dwRefObjID uint32
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        byField_04 uint8
        byField_05 uint8
        byField_06 uint8
        byField_07 uint8
        byField_08 uint8
        byField_09 uint8
        byField_10 uint8
        dwField_11 uint32
        dwField_12 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressUpdate {
        dwRefObjID: number;
        byResult: number;
        byField_02: number;
        byField_03: number;
        byField_04: number;
        byField_05: number;
        byField_06: number;
        byField_07: number;
        byField_08: number;
        byField_09: number;
        byField_10: number;
        dwField_11: number;
        dwField_12: number;
    }
    ```


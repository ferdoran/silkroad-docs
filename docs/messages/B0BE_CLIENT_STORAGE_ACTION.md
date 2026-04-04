# CLIENT_STORAGE_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0BE` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A4A30`, `0x008A4B00` |

## Handler 1: `0x008A4A30`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u32` | 4 | `0x008A4A41` |
| 2 | `dwParam2` | `u32` | 4 | `0x008A4A4F` |

**Total size**: 8 bytes

### String References
| String | Type |
|--------|------|
| `SYSTEM_MONSTER_CAPTURE` | Debug |

### String References
| String | Type |
|--------|------|
| `SKILL_EU_WARLOCK_BLOODA_EXPLOSION_A` | Debug |

### Structure Summary

```
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
```

## Handler 2: `0x008A4B00`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u8` | 1 | `0x008A4B11` |
| 2 | `dwParam2` | `u32` | 4 | `0x008A4B3A` |
| 3 | `byField_03` | `u8` | 1 | `0x008A4B48` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A4B56` |
| 5 | `byField_05` | `u8` | 1 | `0x008A4B64` |
| 6 | `bytesData_5` | `bytes[3]` | 3 | `0x008A4B9D` |

**Total size**: 14 bytes

### String References
| String | Type |
|--------|------|
| `SYSTEM_MONSTER_CAPTURE` | Debug |

### String References
| String | Type |
|--------|------|
| `SKILL_EU_WARLOCK_BLOODA_EXPLOSION_A` | Debug |

### Structure Summary

```
  [   0] dwParam1                       u8
  [   1] dwParam2                       u32
  [   5] byField_03                     u8
  [   6] dwField_04                     u32
  [  10] byField_05                     u8
  [  11] bytesData_5                    bytes[3]
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StorageAction {
        uint32_t dwParam1;
        uint32_t dwParam2;
        uint8_t byField_03;
        uint32_t dwField_04;
        uint8_t byField_05;
        uint8_t bytesData_5;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StorageAction(
        uint dwParam1,
        uint dwParam2,
        byte byField_03,
        uint dwField_04,
        byte byField_05,
        byte bytesData_5
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StorageAction {
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub by_field_03: u8,
        pub dw_field_04: u32,
        pub by_field_05: u8,
        pub bytes_data_5: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type StorageAction struct {
        dwParam1 uint32
        dwParam2 uint32
        byField_03 uint8
        dwField_04 uint32
        byField_05 uint8
        bytesData_5 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StorageAction {
        dwParam1: number;
        dwParam2: number;
        byField_03: number;
        dwField_04: number;
        byField_05: number;
        bytesData_5: number;
    }
    ```


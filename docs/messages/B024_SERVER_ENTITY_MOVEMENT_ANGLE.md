# SERVER_ENTITY_MOVEMENT_ANGLE

> **Corrected name** (server RE): Was `CLIENT_CHARACTER_LIST_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB024` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A5750`, `0x008A4F80` |

## Handler 1: `0x008A5750`

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 |  |
| 2 | `Angle` | `u16` | 2 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A5770` |
| 2 | `byAction` | `u8` | 1 | `0x008A564E` |
| 3 | `byField_03` | `u8` | 1 | `0x008A5662` |
| 4 | `byField_04` | `u8` | 1 | `0x008A5674` |
| 5 | `wField_05` | `u16` | 2 | `0x008A5682` |
| 6 | `byField_06` | `u8` | 1 | `0x008A5789` |

**Total size**: 10 bytes

</details>
### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] byField_03                     u8
  [   6] byField_04                     u8
  [   7] wField_05                      u16
  [   9] byField_06                     u8
```

## Handler 2: `0x008A4F80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A4F92` |
| 2 | `byAction` | `u16` | 2 | `0x008A4FA0` |
| 3 | `bytesData_2` | `bytes[14]` | 14 | `0x008A4FAE` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u16
  [   6] bytesData_2                    bytes[14]
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityMovementAngle {
        uint32_t dwUniqueID;
        uint8_t byAction;
        uint8_t byField_03;
        uint8_t byField_04;
        uint16_t wField_05;
        uint8_t byField_06;
        uint8_t bytesData_2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityMovementAngle(
        uint dwUniqueID,
        byte byAction,
        byte byField_03,
        byte byField_04,
        ushort wField_05,
        byte byField_06,
        byte bytesData_2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityMovementAngle {
        pub dw_unique_id: u32,
        pub by_action: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub w_field_05: u16,
        pub by_field_06: u8,
        pub bytes_data_2: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityMovementAngle struct {
        dwUniqueID uint32
        byAction uint8
        byField_03 uint8
        byField_04 uint8
        wField_05 uint16
        byField_06 uint8
        bytesData_2 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityMovementAngle {
        dwUniqueID: number;
        byAction: number;
        byField_03: number;
        byField_04: number;
        wField_05: number;
        byField_06: number;
        bytesData_2: number;
    }
    ```


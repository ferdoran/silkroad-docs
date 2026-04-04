# SERVER_GUILD_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x747E` |
| Direction | Client → Server |
| Group | Guild/Union |
| Handler(s) | `0x00890AB0`, `0x00890FA0` |

## Handler 1: `0x00890AB0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00890AFB` |
| 2 | `byField_02` | `u8` | 1 | `0x00890B15` |
| 3 | `byField_03` | `u8` | 1 | `0x00890B23` |
| 4 | `byField_04` | `u8` | 1 | `0x00890B31` |
| 5 | `dwField_05` | `u32` | 4 | `0x00890C56` |
| 6 | `dwField_06` | `u32` | 4 | `0x00890C64` |
| 7 | `byField_07` | `u8` | 1 | `0x00890C72` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `dwField_10` | `u32` | 4 | `0x00890C8C` |
| 11 | `byField_11` | `u8` | 1 | `0x00890C9A` |
| 12 | `byField_12` | `u8` | 1 | `0x00890CA8` |
| 13 | `dwField_13` | `u32` | 4 | `0x00890CB6` |
| 14 | `wField_14` | `u16` | 2 | `0x004F7A7D` |
| 15 | `bytesData_14` | `bytes` | variable | `0x004F7AB9` |
| 16 | `dwField_16` | `u32` | 4 | `0x00890CD3` |
| 17 | `byField_17` | `u8` | 1 | `0x00890CE4` |
| 18 | `dwField_18` | `u32` | 4 | `0x00890CF5` |
| 19 | `dwField_19` | `u32` | 4 | `0x00890D06` |
| 20 | `wField_20` | `u16` | 2 | `0x00890F4D` |

**Minimum size**: 42 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] byField_07                     u8
  [  13] wField_08                      u16
  [  15] bytesData_8                    bytes  (variable length)
  [   0] dwField_10                     u32
  [   4] byField_11                     u8
  [   5] byField_12                     u8
  [   6] dwField_13                     u32
  [  10] wField_14                      u16
  [  12] bytesData_14                   bytes  (variable length)
  [   0] dwField_16                     u32
  [   4] byField_17                     u8
  [   5] dwField_18                     u32
  [   9] dwField_19                     u32
  [  13] wField_20                      u16
```

## Handler 2: `0x00890FA0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00890FED` |
| 2 | `dwField_02` | `u32` | 4 | `0x00890FFB` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088F4DD` |
| 4 | `dwField_04` | `u32` | 4 | `0x0088F4EA` |
| 5 | `byField_05` | `u8` | 1 | `0x0088F4F7` |
| 6 | `byField_06` | `u8` | 1 | `0x0088F504` |
| 7 | `dwField_07` | `u32` | 4 | `0x0088F511` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |

**Minimum size**: 24 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] byField_05                     u8
  [  17] byField_06                     u8
  [  18] dwField_07                     u32
  [  22] wField_08                      u16
  [  24] bytesData_8                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildData {
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint8_t byField_07;
        uint16_t wField_08;
        std::vector<uint8_t> bytesData_8;
        uint32_t dwField_10;
        uint8_t byField_11;
        uint8_t byField_12;
        uint32_t dwField_13;
        uint16_t wField_14;
        std::vector<uint8_t> bytesData_14;
        uint32_t dwField_16;
        uint8_t byField_17;
        uint32_t dwField_18;
        uint32_t dwField_19;
        uint16_t wField_20;
        uint32_t dwRefObjID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint32_t dwField_04;
        uint8_t byField_05;
        uint8_t byField_06;
        uint32_t dwField_07;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildData(
        byte byResult,
        byte byField_02,
        byte byField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06,
        byte byField_07,
        ushort wField_08,
        byte[] bytesData_8,
        uint dwField_10,
        byte byField_11,
        byte byField_12,
        uint dwField_13,
        ushort wField_14,
        byte[] bytesData_14,
        uint dwField_16,
        byte byField_17,
        uint dwField_18,
        uint dwField_19,
        ushort wField_20,
        uint dwRefObjID,
        uint dwField_02,
        uint dwField_03,
        uint dwField_04,
        byte byField_05,
        byte byField_06,
        uint dwField_07
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildData {
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub by_field_07: u8,
        pub w_field_08: u16,
        pub bytes_data_8: Vec<u8>,
        pub dw_field_10: u32,
        pub by_field_11: u8,
        pub by_field_12: u8,
        pub dw_field_13: u32,
        pub w_field_14: u16,
        pub bytes_data_14: Vec<u8>,
        pub dw_field_16: u32,
        pub by_field_17: u8,
        pub dw_field_18: u32,
        pub dw_field_19: u32,
        pub w_field_20: u16,
        pub dw_ref_obj_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub dw_field_04: u32,
        pub by_field_05: u8,
        pub by_field_06: u8,
        pub dw_field_07: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildData struct {
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
        byField_07 uint8
        wField_08 uint16
        bytesData_8 []byte
        dwField_10 uint32
        byField_11 uint8
        byField_12 uint8
        dwField_13 uint32
        wField_14 uint16
        bytesData_14 []byte
        dwField_16 uint32
        byField_17 uint8
        dwField_18 uint32
        dwField_19 uint32
        wField_20 uint16
        dwRefObjID uint32
        dwField_02 uint32
        dwField_03 uint32
        dwField_04 uint32
        byField_05 uint8
        byField_06 uint8
        dwField_07 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildData {
        byResult: number;
        byField_02: number;
        byField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
        byField_07: number;
        wField_08: number;
        bytesData_8: Uint8Array;
        dwField_10: number;
        byField_11: number;
        byField_12: number;
        dwField_13: number;
        wField_14: number;
        bytesData_14: Uint8Array;
        dwField_16: number;
        byField_17: number;
        dwField_18: number;
        dwField_19: number;
        wField_20: number;
        dwRefObjID: number;
        dwField_02: number;
        dwField_03: number;
        dwField_04: number;
        byField_05: number;
        byField_06: number;
        dwField_07: number;
    }
    ```


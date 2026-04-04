# SERVER_STALL_CREATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3C80` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089C620`, `0x008A2110` |

## Handler 1: `0x0089C620`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089C66B` |
| 2 | `byField_02` | `u8` | 1 | `0x0089C6EB` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089C70A` |
| 4 | `byField_04` | `u8` | 1 | `0x0089C718` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x0089C737` |
| 8 | `byField_08` | `u8` | 1 | `0x0089C745` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089C753` |
| 10 | `wField_10` | `u16` | 2 | `0x0089C8E8` |

**Minimum size**: 17 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_DISSOLUTION_SUCCESS` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_ANNOUNCE` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_OTHER_USER` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT_ANNOUNCE` | UI |
| `UIIT_MSG_TC_MACHING_JOINING_MEMBER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] wField_05                      u16
  [   9] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] byField_08                     u8
  [   2] dwField_09                     u32
  [   6] wField_10                      u16
```

## Handler 2: `0x008A2110`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A215C` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A21F5` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A2203` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A2211` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x008A222E` |
| 8 | `byField_08` | `u8` | 1 | `0x008A223C` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008A224E` |
| 10 | `byField_10` | `u8` | 1 | `0x008A225C` |
| 11 | `byField_11` | `u8` | 1 | `0x008A226A` |
| 12 | `dwField_12` | `u32` | 4 | `0x008A2278` |
| 13 | `byField_13` | `u8` | 1 | `0x008A2286` |
| 14 | `dwField_14` | `u32` | 4 | `0x008A2294` |
| 15 | `wField_15` | `u16` | 2 | `0x008A22A2` |
| 16 | `wField_16` | `u16` | 2 | `0x008A22B0` |
| 17 | `wField_17` | `u16` | 2 | `0x008A22BE` |
| 18 | `wField_18` | `u16` | 2 | `0x008A22CC` |
| 19 | `dwField_19` | `u32` | 4 | `0x008A25BE` |
| 20 | `byField_20` | `u8` | 1 | `0x008A25CC` |

**Minimum size**: 41 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_DISSOLUTION_SUCCESS` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_ANNOUNCE` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_OTHER_USER` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT_ANNOUNCE` | UI |
| `UIIT_MSG_TC_MACHING_JOINING_MEMBER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] dwField_04                     u32
  [  13] wField_05                      u16
  [  15] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] byField_08                     u8
  [   2] bytesData_8                    bytes  (variable length)
  [   0] byField_10                     u8
  [   1] byField_11                     u8
  [   2] dwField_12                     u32
  [   6] byField_13                     u8
  [   7] dwField_14                     u32
  [  11] wField_15                      u16
  [  13] wField_16                      u16
  [  15] wField_17                      u16
  [  17] wField_18                      u16
  [  19] dwField_19                     u32
  [  23] byField_20                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallCreate {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint16_t wField_05;
        std::vector<uint8_t> bytesData_5;
        uint8_t byField_07;
        uint8_t byField_08;
        uint32_t dwField_09;
        uint16_t wField_10;
        uint32_t dwField_02;
        uint32_t dwField_04;
        std::vector<uint8_t> bytesData_8;
        uint8_t byField_10;
        uint8_t byField_11;
        uint32_t dwField_12;
        uint8_t byField_13;
        uint32_t dwField_14;
        uint16_t wField_15;
        uint16_t wField_16;
        uint16_t wField_17;
        uint16_t wField_18;
        uint32_t dwField_19;
        uint8_t byField_20;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallCreate(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        byte byField_04,
        ushort wField_05,
        byte[] bytesData_5,
        byte byField_07,
        byte byField_08,
        uint dwField_09,
        ushort wField_10,
        uint dwField_02,
        uint dwField_04,
        byte[] bytesData_8,
        byte byField_10,
        byte byField_11,
        uint dwField_12,
        byte byField_13,
        uint dwField_14,
        ushort wField_15,
        ushort wField_16,
        ushort wField_17,
        ushort wField_18,
        uint dwField_19,
        byte byField_20
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallCreate {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub w_field_05: u16,
        pub bytes_data_5: Vec<u8>,
        pub by_field_07: u8,
        pub by_field_08: u8,
        pub dw_field_09: u32,
        pub w_field_10: u16,
        pub dw_field_02: u32,
        pub dw_field_04: u32,
        pub bytes_data_8: Vec<u8>,
        pub by_field_10: u8,
        pub by_field_11: u8,
        pub dw_field_12: u32,
        pub by_field_13: u8,
        pub dw_field_14: u32,
        pub w_field_15: u16,
        pub w_field_16: u16,
        pub w_field_17: u16,
        pub w_field_18: u16,
        pub dw_field_19: u32,
        pub by_field_20: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallCreate struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        byField_04 uint8
        wField_05 uint16
        bytesData_5 []byte
        byField_07 uint8
        byField_08 uint8
        dwField_09 uint32
        wField_10 uint16
        dwField_02 uint32
        dwField_04 uint32
        bytesData_8 []byte
        byField_10 uint8
        byField_11 uint8
        dwField_12 uint32
        byField_13 uint8
        dwField_14 uint32
        wField_15 uint16
        wField_16 uint16
        wField_17 uint16
        wField_18 uint16
        dwField_19 uint32
        byField_20 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallCreate {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        byField_04: number;
        wField_05: number;
        bytesData_5: Uint8Array;
        byField_07: number;
        byField_08: number;
        dwField_09: number;
        wField_10: number;
        dwField_02: number;
        dwField_04: number;
        bytesData_8: Uint8Array;
        byField_10: number;
        byField_11: number;
        dwField_12: number;
        byField_13: number;
        dwField_14: number;
        wField_15: number;
        wField_16: number;
        wField_17: number;
        wField_18: number;
        dwField_19: number;
        byField_20: number;
    }
    ```


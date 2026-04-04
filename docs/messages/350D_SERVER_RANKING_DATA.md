# SERVER_RANKING_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x350D` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089AA00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AA4A` |
| 2 | `byField_02` | `u8` | 1 | `0x0089AA71` |
| 3 | `dwField_03` | `u32` | 4 | `0x005E6EC2` |
| 4 | `byField_04` | `u8` | 1 | `0x005E6ED0` |
| 5 | `dwField_05` | `u32` | 4 | `0x008BE549` |
| 6 | `byField_06` | `u8` | 1 | `0x008BE5DD` |
| 7 | `ullField_07` | `u64` | 8 | `0x008BE5ED` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BE5FB` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008BE642` |
| 10 | `ullField_10` | `u64` | 8 | `0x008BE652` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE662` |
| 12 | `wField_12` | `u16` | 2 | `0x008BE6C9` |
| 13 | `wField_13` | `u16` | 2 | `0x008BE75F` |
| 14 | `byField_14` | `u8` | 1 | `0x008BE830` |
| 15 | `dwField_15` | `u32` | 4 | `0x008BE849` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE8F9` |
| 17 | `byField_17` | `u8` | 1 | `0x008BE927` |
| 18 | `byField_18` | `u8` | 1 | `0x008BE97D` |
| 19 | `dwField_19` | `u32` | 4 | `0x008BE98B` |
| 20 | `dwField_20` | `u32` | 4 | `0x008BE999` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE9DA` |
| 22 | `byField_22` | `u8` | 1 | `0x008BE9E8` |
| 23 | `dwField_23` | `u32` | 4 | `0x008BEAAE` |
| 24 | `wField_24` | `u16` | 2 | `0x0089AB01` |

**Minimum size**: 70 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] dwField_05                     u32
  [  11] byField_06                     u8
  [  12] ullField_07                    u64
  [  20] dwField_08                     u32
  [  24] bytesData_8                    bytes  (variable length)
  [   0] ullField_10                    u64
  [   8] dwField_11                     u32
  [  12] wField_12                      u16
  [  14] wField_13                      u16
  [  16] byField_14                     u8
  [  17] dwField_15                     u32
  [  21] dwField_16                     u32
  [  25] byField_17                     u8
  [  26] byField_18                     u8
  [  27] dwField_19                     u32
  [  31] dwField_20                     u32
  [  35] dwField_21                     u32
  [  39] byField_22                     u8
  [  40] dwField_23                     u32
  [  44] wField_24                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingData {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint8_t byField_06;
        uint64_t ullField_07;
        uint32_t dwField_08;
        std::vector<uint8_t> bytesData_8;
        uint64_t ullField_10;
        uint32_t dwField_11;
        uint16_t wField_12;
        uint16_t wField_13;
        uint8_t byField_14;
        uint32_t dwField_15;
        uint32_t dwField_16;
        uint8_t byField_17;
        uint8_t byField_18;
        uint32_t dwField_19;
        uint32_t dwField_20;
        uint32_t dwField_21;
        uint8_t byField_22;
        uint32_t dwField_23;
        uint16_t wField_24;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingData(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        byte byField_06,
        ulong ullField_07,
        uint dwField_08,
        byte[] bytesData_8,
        ulong ullField_10,
        uint dwField_11,
        ushort wField_12,
        ushort wField_13,
        byte byField_14,
        uint dwField_15,
        uint dwField_16,
        byte byField_17,
        byte byField_18,
        uint dwField_19,
        uint dwField_20,
        uint dwField_21,
        byte byField_22,
        uint dwField_23,
        ushort wField_24
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingData {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub by_field_06: u8,
        pub ull_field_07: u64,
        pub dw_field_08: u32,
        pub bytes_data_8: Vec<u8>,
        pub ull_field_10: u64,
        pub dw_field_11: u32,
        pub w_field_12: u16,
        pub w_field_13: u16,
        pub by_field_14: u8,
        pub dw_field_15: u32,
        pub dw_field_16: u32,
        pub by_field_17: u8,
        pub by_field_18: u8,
        pub dw_field_19: u32,
        pub dw_field_20: u32,
        pub dw_field_21: u32,
        pub by_field_22: u8,
        pub dw_field_23: u32,
        pub w_field_24: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingData struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        byField_06 uint8
        ullField_07 uint64
        dwField_08 uint32
        bytesData_8 []byte
        ullField_10 uint64
        dwField_11 uint32
        wField_12 uint16
        wField_13 uint16
        byField_14 uint8
        dwField_15 uint32
        dwField_16 uint32
        byField_17 uint8
        byField_18 uint8
        dwField_19 uint32
        dwField_20 uint32
        dwField_21 uint32
        byField_22 uint8
        dwField_23 uint32
        wField_24 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingData {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        byField_06: number;
        ullField_07: bigint;
        dwField_08: number;
        bytesData_8: Uint8Array;
        ullField_10: bigint;
        dwField_11: number;
        wField_12: number;
        wField_13: number;
        byField_14: number;
        dwField_15: number;
        dwField_16: number;
        byField_17: number;
        byField_18: number;
        dwField_19: number;
        dwField_20: number;
        dwField_21: number;
        byField_22: number;
        dwField_23: number;
        wField_24: number;
    }
    ```


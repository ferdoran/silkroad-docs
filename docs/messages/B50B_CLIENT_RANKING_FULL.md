# CLIENT_RANKING_FULL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB50B` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089AC00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AC25` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089AC62` |
| 3 | `byField_03` | `u8` | 1 | `0x0089AC70` |
| 4 | `dwField_04` | `u32` | 4 | `0x008BB144` |
| 5 | `wField_05` | `u16` | 2 | `0x008BB174` |
| 6 | `dwField_06` | `u32` | 4 | `0x008BB192` |
| 7 | `dwField_07` | `u32` | 4 | `0x008BB1A0` |
| 8 | `wField_08` | `u16` | 2 | `0x008BB1C4` |
| 9 | `dwField_09` | `u32` | 4 | `0x008BB1DE` |
| 10 | `dwField_10` | `u32` | 4 | `0x008BE549` |
| 11 | `byField_11` | `u8` | 1 | `0x008BE5DD` |
| 12 | `ullField_12` | `u64` | 8 | `0x008BE5ED` |
| 13 | `dwField_13` | `u32` | 4 | `0x008BE5FB` |
| 14 | `bytesData_13` | `bytes` | variable | `0x008BE642` |
| 15 | `ullField_15` | `u64` | 8 | `0x008BE652` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE662` |
| 17 | `byField_17` | `u8` | 1 | `0x008BCE4B` |
| 18 | `ullField_18` | `u64` | 8 | `0x008BCE9F` |
| 19 | `byField_19` | `u8` | 1 | `0x008BB08E` |
| 20 | `byField_20` | `u8` | 1 | `0x008BB09C` |
| 21 | `byField_21` | `u8` | 1 | `0x008BB0BA` |
| 22 | `ullField_22` | `u64` | 8 | `0x008BB0C8` |
| 23 | `wField_23` | `u16` | 2 | `0x008BE6C9` |
| 24 | `wField_24` | `u16` | 2 | `0x004F7A7D` |
| 25 | `bytesData_24` | `bytes` | variable | `0x004F7AB9` |
| 26 | `dwField_26` | `u32` | 4 | `0x004F74CA` |
| 27 | `wField_27` | `u16` | 2 | `0x008BE75F` |
| 28 | `byField_28` | `u8` | 1 | `0x004F746A` |
| 29 | `byField_29` | `u8` | 1 | `0x008BE830` |
| 30 | `dwField_30` | `u32` | 4 | `0x008BE849` |
| 31 | `dwField_31` | `u32` | 4 | `0x008BE8F9` |
| 32 | `byField_32` | `u8` | 1 | `0x008BE927` |
| 33 | `byField_33` | `u8` | 1 | `0x008BE97D` |
| 34 | `dwField_34` | `u32` | 4 | `0x008BE98B` |
| 35 | `dwField_35` | `u32` | 4 | `0x008BE999` |
| 36 | `dwField_36` | `u32` | 4 | `0x008BE9DA` |
| 37 | `byField_37` | `u8` | 1 | `0x008BE9E8` |
| 38 | `dwField_38` | `u32` | 4 | `0x008BEAAE` |

**Minimum size**: 114 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] byField_03                     u8
  [   6] dwField_04                     u32
  [  10] wField_05                      u16
  [  12] dwField_06                     u32
  [  16] dwField_07                     u32
  [  20] wField_08                      u16
  [  22] dwField_09                     u32
  [  26] dwField_10                     u32
  [  30] byField_11                     u8
  [  31] ullField_12                    u64
  [  39] dwField_13                     u32
  [  43] bytesData_13                   bytes  (variable length)
  [   0] ullField_15                    u64
  [   8] dwField_16                     u32
  [  12] byField_17                     u8
  [  13] ullField_18                    u64
  [  21] byField_19                     u8
  [  22] byField_20                     u8
  [  23] byField_21                     u8
  [  24] ullField_22                    u64
  [  32] wField_23                      u16
  [  34] wField_24                      u16
  [  36] bytesData_24                   bytes  (variable length)
  [   0] dwField_26                     u32
  [   4] wField_27                      u16
  [   6] byField_28                     u8
  [   7] byField_29                     u8
  [   8] dwField_30                     u32
  [  12] dwField_31                     u32
  [  16] byField_32                     u8
  [  17] byField_33                     u8
  [  18] dwField_34                     u32
  [  22] dwField_35                     u32
  [  26] dwField_36                     u32
  [  30] byField_37                     u8
  [  31] dwField_38                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingFull {
        uint8_t byResult;
        uint32_t dwField_02;
        uint8_t byField_03;
        uint32_t dwField_04;
        uint16_t wField_05;
        uint32_t dwField_06;
        uint32_t dwField_07;
        uint16_t wField_08;
        uint32_t dwField_09;
        uint32_t dwField_10;
        uint8_t byField_11;
        uint64_t ullField_12;
        uint32_t dwField_13;
        std::vector<uint8_t> bytesData_13;
        uint64_t ullField_15;
        uint32_t dwField_16;
        uint8_t byField_17;
        uint64_t ullField_18;
        uint8_t byField_19;
        uint8_t byField_20;
        uint8_t byField_21;
        uint64_t ullField_22;
        uint16_t wField_23;
        uint16_t wField_24;
        std::vector<uint8_t> bytesData_24;
        uint32_t dwField_26;
        uint16_t wField_27;
        uint8_t byField_28;
        uint8_t byField_29;
        uint32_t dwField_30;
        uint32_t dwField_31;
        uint8_t byField_32;
        uint8_t byField_33;
        uint32_t dwField_34;
        uint32_t dwField_35;
        uint32_t dwField_36;
        uint8_t byField_37;
        uint32_t dwField_38;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingFull(
        byte byResult,
        uint dwField_02,
        byte byField_03,
        uint dwField_04,
        ushort wField_05,
        uint dwField_06,
        uint dwField_07,
        ushort wField_08,
        uint dwField_09,
        uint dwField_10,
        byte byField_11,
        ulong ullField_12,
        uint dwField_13,
        byte[] bytesData_13,
        ulong ullField_15,
        uint dwField_16,
        byte byField_17,
        ulong ullField_18,
        byte byField_19,
        byte byField_20,
        byte byField_21,
        ulong ullField_22,
        ushort wField_23,
        ushort wField_24,
        byte[] bytesData_24,
        uint dwField_26,
        ushort wField_27,
        byte byField_28,
        byte byField_29,
        uint dwField_30,
        uint dwField_31,
        byte byField_32,
        byte byField_33,
        uint dwField_34,
        uint dwField_35,
        uint dwField_36,
        byte byField_37,
        uint dwField_38
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingFull {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub by_field_03: u8,
        pub dw_field_04: u32,
        pub w_field_05: u16,
        pub dw_field_06: u32,
        pub dw_field_07: u32,
        pub w_field_08: u16,
        pub dw_field_09: u32,
        pub dw_field_10: u32,
        pub by_field_11: u8,
        pub ull_field_12: u64,
        pub dw_field_13: u32,
        pub bytes_data_13: Vec<u8>,
        pub ull_field_15: u64,
        pub dw_field_16: u32,
        pub by_field_17: u8,
        pub ull_field_18: u64,
        pub by_field_19: u8,
        pub by_field_20: u8,
        pub by_field_21: u8,
        pub ull_field_22: u64,
        pub w_field_23: u16,
        pub w_field_24: u16,
        pub bytes_data_24: Vec<u8>,
        pub dw_field_26: u32,
        pub w_field_27: u16,
        pub by_field_28: u8,
        pub by_field_29: u8,
        pub dw_field_30: u32,
        pub dw_field_31: u32,
        pub by_field_32: u8,
        pub by_field_33: u8,
        pub dw_field_34: u32,
        pub dw_field_35: u32,
        pub dw_field_36: u32,
        pub by_field_37: u8,
        pub dw_field_38: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingFull struct {
        byResult uint8
        dwField_02 uint32
        byField_03 uint8
        dwField_04 uint32
        wField_05 uint16
        dwField_06 uint32
        dwField_07 uint32
        wField_08 uint16
        dwField_09 uint32
        dwField_10 uint32
        byField_11 uint8
        ullField_12 uint64
        dwField_13 uint32
        bytesData_13 []byte
        ullField_15 uint64
        dwField_16 uint32
        byField_17 uint8
        ullField_18 uint64
        byField_19 uint8
        byField_20 uint8
        byField_21 uint8
        ullField_22 uint64
        wField_23 uint16
        wField_24 uint16
        bytesData_24 []byte
        dwField_26 uint32
        wField_27 uint16
        byField_28 uint8
        byField_29 uint8
        dwField_30 uint32
        dwField_31 uint32
        byField_32 uint8
        byField_33 uint8
        dwField_34 uint32
        dwField_35 uint32
        dwField_36 uint32
        byField_37 uint8
        dwField_38 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingFull {
        byResult: number;
        dwField_02: number;
        byField_03: number;
        dwField_04: number;
        wField_05: number;
        dwField_06: number;
        dwField_07: number;
        wField_08: number;
        dwField_09: number;
        dwField_10: number;
        byField_11: number;
        ullField_12: bigint;
        dwField_13: number;
        bytesData_13: Uint8Array;
        ullField_15: bigint;
        dwField_16: number;
        byField_17: number;
        ullField_18: bigint;
        byField_19: number;
        byField_20: number;
        byField_21: number;
        ullField_22: bigint;
        wField_23: number;
        wField_24: number;
        bytesData_24: Uint8Array;
        dwField_26: number;
        wField_27: number;
        byField_28: number;
        byField_29: number;
        dwField_30: number;
        dwField_31: number;
        byField_32: number;
        byField_33: number;
        dwField_34: number;
        dwField_35: number;
        dwField_36: number;
        byField_37: number;
        dwField_38: number;
    }
    ```


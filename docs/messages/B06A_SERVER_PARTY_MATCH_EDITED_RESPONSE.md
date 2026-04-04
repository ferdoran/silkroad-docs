# SERVER_PARTY_MATCH_EDITED_RESPONSE

> Previously documented as `CLIENT_ENTITY_SPAWN_REQUEST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB06A` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883F90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00883FCC` |
| 2 | `wErrorCode` | `u32` | 4 | `0x0088378D` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088379A` |
| 4 | `byField_04` | `u8` | 1 | `0x008837A7` |
| 5 | `byField_05` | `u8` | 1 | `0x008837B4` |
| 6 | `byField_06` | `u8` | 1 | `0x008837C1` |
| 7 | `byField_07` | `u8` | 1 | `0x008837CE` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `wField_10` | `u16` | 2 | `0x00884089` |

**Minimum size**: 17 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_PARTYMATCH_RECORD_COMPLETE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wErrorCode                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] byField_05                     u8
  [  11] byField_06                     u8
  [  12] byField_07                     u8
  [  13] wField_08                      u16
  [  15] bytesData_8                    bytes  (variable length)
  [   0] wField_10                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpawnRequest {
        uint8_t byResult;
        uint32_t wErrorCode;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint8_t byField_05;
        uint8_t byField_06;
        uint8_t byField_07;
        uint16_t wField_08;
        std::vector<uint8_t> bytesData_8;
        uint16_t wField_10;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySpawnRequest(
        byte byResult,
        uint wErrorCode,
        uint dwField_03,
        byte byField_04,
        byte byField_05,
        byte byField_06,
        byte byField_07,
        ushort wField_08,
        byte[] bytesData_8,
        ushort wField_10
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpawnRequest {
        pub by_result: u8,
        pub w_error_code: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub by_field_05: u8,
        pub by_field_06: u8,
        pub by_field_07: u8,
        pub w_field_08: u16,
        pub bytes_data_8: Vec<u8>,
        pub w_field_10: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpawnRequest struct {
        byResult uint8
        wErrorCode uint32
        dwField_03 uint32
        byField_04 uint8
        byField_05 uint8
        byField_06 uint8
        byField_07 uint8
        wField_08 uint16
        bytesData_8 []byte
        wField_10 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySpawnRequest {
        byResult: number;
        wErrorCode: number;
        dwField_03: number;
        byField_04: number;
        byField_05: number;
        byField_06: number;
        byField_07: number;
        wField_08: number;
        bytesData_8: Uint8Array;
        wField_10: number;
    }
    ```


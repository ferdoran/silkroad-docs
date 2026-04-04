# CLIENT_BATTLE_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB51A` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089F010` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0089F062` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089F070` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089F07E` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 14 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] wField_04                      u16
  [  14] bytesData_4                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleUpdate {
        uint32_t dwUniqueID;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleUpdate(
        uint dwUniqueID,
        uint dwField_02,
        uint dwField_03,
        ushort wField_04,
        byte[] bytesData_4
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleUpdate {
        pub dw_unique_id: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleUpdate struct {
        dwUniqueID uint32
        dwField_02 uint32
        dwField_03 uint32
        wField_04 uint16
        bytesData_4 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleUpdate {
        dwUniqueID: number;
        dwField_02: number;
        dwField_03: number;
        wField_04: number;
        bytesData_4: Uint8Array;
    }
    ```


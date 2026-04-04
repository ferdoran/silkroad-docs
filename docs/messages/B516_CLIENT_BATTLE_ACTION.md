# CLIENT_BATTLE_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB516` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x00891080` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008910C8` |
| 2 | `byField_02` | `u8` | 1 | `0x008910FB` |
| 3 | `byField_03` | `u8` | 1 | `0x00891109` |
| 4 | `byField_04` | `u8` | 1 | `0x00891117` |
| 5 | `byField_05` | `u8` | 1 | `0x008911CB` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_SAFETRADE_PROGRESS` | UI |
| `UIIT_MSG_SAFETRADE_NUMBER_ERR_LIMIT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] byField_05                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleAction {
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint8_t byField_04;
        uint8_t byField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleAction(
        byte byResult,
        byte byField_02,
        byte byField_03,
        byte byField_04,
        byte byField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleAction {
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub by_field_05: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleAction struct {
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        byField_04 uint8
        byField_05 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleAction {
        byResult: number;
        byField_02: number;
        byField_03: number;
        byField_04: number;
        byField_05: number;
    }
    ```


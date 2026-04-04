# SERVER_PET_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30D4` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7D20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUpdateType` | `u8` | 1 | `0x008A7D31` |
| 2 | `dwPetUID` | `u32` | 4 | `0x008A7D4C` |
| 3 | `byParam` | `u8` | 1 | `0x008A7D5A` |
| 4 | `dwValue` | `u32` | 4 | `0x008A7D68` |

**Total size**: 10 bytes

### String References
| String | Type |
|--------|------|
| `pCOSInfo->IsCashPet()` | Debug |
| `pCOSInfo->IsGoldPet()` | Debug |

### Structure Summary

```
  [   0] byUpdateType                   u8
  [   1] dwPetUID                       u32
  [   5] byParam                        u8
  [   6] dwValue                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetUpdate {
        uint8_t byUpdateType;
        uint32_t dwPetUID;
        uint8_t byParam;
        uint32_t dwValue;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetUpdate(
        byte byUpdateType,
        uint dwPetUID,
        byte byParam,
        uint dwValue
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetUpdate {
        pub by_update_type: u8,
        pub dw_pet_uid: u32,
        pub by_param: u8,
        pub dw_value: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetUpdate struct {
        byUpdateType uint8
        dwPetUID uint32
        byParam uint8
        dwValue uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetUpdate {
        byUpdateType: number;
        dwPetUID: number;
        byParam: number;
        dwValue: number;
    }
    ```


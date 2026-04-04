# SERVER_PET_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30D1` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4980` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwPetRefID` | `u32` | 4 | `0x00A56731` |
| 2 | `dwOwnerUID` | `u32` | 4 | `0x00A5673F` |
| 3 | `wHappiness` | `u16` | 2 | `0x00A5674D` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] dwPetRefID                     u32
  [   4] dwOwnerUID                     u32
  [   8] wHappiness                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetData {
        uint32_t dwPetRefID;
        uint32_t dwOwnerUID;
        uint16_t wHappiness;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetData(
        uint dwPetRefID,
        uint dwOwnerUID,
        ushort wHappiness
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetData {
        pub dw_pet_ref_id: u32,
        pub dw_owner_uid: u32,
        pub w_happiness: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetData struct {
        dwPetRefID uint32
        dwOwnerUID uint32
        wHappiness uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetData {
        dwPetRefID: number;
        dwOwnerUID: number;
        wHappiness: number;
    }
    ```


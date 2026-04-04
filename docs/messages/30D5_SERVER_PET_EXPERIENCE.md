# SERVER_PET_EXPERIENCE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30D5` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00881280` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwPetExp` | `u32` | 4 | `0x0088128B` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwPetExp                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetExperience {
        uint32_t dwPetExp;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetExperience(
        uint dwPetExp
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetExperience {
        pub dw_pet_exp: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetExperience struct {
        dwPetExp uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetExperience {
        dwPetExp: number;
    }
    ```


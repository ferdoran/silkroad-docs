# SERVER_ENTITY_POSITION_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3200` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008A5280` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A5291` |
| 2 | `dwPosX` | `u32` | 4 | `0x008A529F` |
| 3 | `dwPosZ` | `u32` | 4 | `0x008A52AD` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwPosX                         u32
  [   8] dwPosZ                         u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityPositionUpdate {
        uint32_t dwUniqueID;
        uint32_t dwPosX;
        uint32_t dwPosZ;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityPositionUpdate(
        uint dwUniqueID,
        uint dwPosX,
        uint dwPosZ
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityPositionUpdate {
        pub dw_unique_id: u32,
        pub dw_pos_x: u32,
        pub dw_pos_z: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityPositionUpdate struct {
        dwUniqueID uint32
        dwPosX uint32
        dwPosZ uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityPositionUpdate {
        dwUniqueID: number;
        dwPosX: number;
        dwPosZ: number;
    }
    ```


# SERVER_ENTITY_MOVEMENT

> **Corrected name** (server RE): Was `CLIENT_CHARACTER_CREATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB021` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872010` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `u32` | 4 |  |
| 2 | `hasMovement` | `bool` | 1 |  |
| 3 | `unk` | `u16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() |
| 4 | `unk` | `i32` | 4 | if(hasMovement) → if(currentPosition.inDungeon() |
| 5 | `unk` | `u16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() |
| 6 | `unk` | `bool` | 1 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() |
| 7 | `oldRegion` | `u16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |
| 8 | `Angle` | `u16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |
| 9 | `unkShort01` | `i16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |
| 10 | `unkShort02` | `i16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |
| 11 | `unkShort03` | `i16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |
| 12 | `unkShort04` | `i16` | 2 | if(hasMovement) → if(currentPosition.inDungeon() → if(entity == InfoManager.Character) → if(xTranslate == 0) → if(yTranslate == 0) → if(yTranslate < 0 || xTranslate < 0) → if(xTranslate > 0) → if(packet.ReadBool() → if(hasMovement) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087201B` |

**Total size**: 1 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityMovement {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityMovement(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityMovement {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityMovement struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityMovement {
        byResult: number;
    }
    ```


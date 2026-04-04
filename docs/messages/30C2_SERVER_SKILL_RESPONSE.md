# SERVER_SKILL_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30C2` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A8FC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A8FCE` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct SkillResponse {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record SkillResponse(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct SkillResponse {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type SkillResponse struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface SkillResponse {
        byResult: number;
    }
    ```


# CLIENT_ACADEMY_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB119` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0088D690` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088D69F` |
| 2 | `byAction` | `u8` | 1 | `0x0088D6AD` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] byAction                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyRequest {
        uint8_t byType;
        uint8_t byAction;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyRequest(
        byte byType,
        byte byAction
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyRequest {
        pub by_type: u8,
        pub by_action: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyRequest struct {
        byType uint8
        byAction uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyRequest {
        byType: number;
        byAction: number;
    }
    ```


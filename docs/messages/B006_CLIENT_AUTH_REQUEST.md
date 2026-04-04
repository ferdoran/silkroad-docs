# CLIENT_AUTH_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB006` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0086DB40` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byLocale` | `u8` | 1 | `0x0086DB4F` |
| 2 | `byVersion` | `u8` | 1 | `0x0086DB65` |
| 3 | `byPlatform` | `u8` | 1 | `0x0086DB73` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byLocale                       u8
  [   1] byVersion                      u8
  [   2] byPlatform                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AuthRequest {
        uint8_t byLocale;
        uint8_t byVersion;
        uint8_t byPlatform;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AuthRequest(
        byte byLocale,
        byte byVersion,
        byte byPlatform
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AuthRequest {
        pub by_locale: u8,
        pub by_version: u8,
        pub by_platform: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type AuthRequest struct {
        byLocale uint8
        byVersion uint8
        byPlatform uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AuthRequest {
        byLocale: number;
        byVersion: number;
        byPlatform: number;
    }
    ```


# SERVER_NPC_CLOSE_RESPONSE

> Previously documented as `CLIENT_GAME_OPTION` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB04B` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00888E30` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00888E41` |
| 2 | `byLockFlag` | `u8` | 1 | `0x00888E74` |
| 3 | `byConfirm` | `u8` | 1 | `0x00888F44` |

**Total size**: 3 bytes

</details>
### String References
| String | Type |
|--------|------|
| `Ghacha` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byLockFlag                     u8
  [   2] byConfirm                      u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GameOption {
        uint8_t byResult;
        uint8_t byLockFlag;
        uint8_t byConfirm;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GameOption(
        byte byResult,
        byte byLockFlag,
        byte byConfirm
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GameOption {
        pub by_result: u8,
        pub by_lock_flag: u8,
        pub by_confirm: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type GameOption struct {
        byResult uint8
        byLockFlag uint8
        byConfirm uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GameOption {
        byResult: number;
        byLockFlag: number;
        byConfirm: number;
    }
    ```


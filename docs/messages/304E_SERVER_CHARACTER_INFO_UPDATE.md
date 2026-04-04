# SERVER_CHARACTER_INFO_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_UPDATE_STATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x304E` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A97C0` |

### Fields (Server RE)

Switched structure based on `UpdateType`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UpdateType` | `u8` | 1 | Determines payload format |

**UpdateType values:**

| UpdateType | Payload | Description |
|------------|---------|-------------|
| 1 | `u64 Gold` | Current gold amount |
| 2 | `u32 SP` | Current skill points |
| 4 | `u8 BerserkPoints` | Current berserk points |

### Structure Summary

```
  [   0] UpdateType                     u8
  switch UpdateType:
    case 1:  [1] Gold                   u64
    case 2:  [1] SP                     u32
    case 4:  [1] BerserkPoints          u8
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A980B` |
| 2 | `ullState1` | `u64` | 8 | `0x008A9819` |
| 3 | `ullState2` | `u64` | 8 | `0x008A9827` |
| 4 | `byFlag` | `u8` | 1 | `0x008A9835` |
| 5 | `dwParam1` | `u32` | 4 | `0x008A9851` |
| 6 | `dwParam2` | `u32` | 4 | `0x008A987C` |
| 7 | `dwParam3` | `u32` | 4 | `0x008A988A` |
| 8 | `wParam4` | `u16` | 2 | `0x008A997D` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterInfoUpdate {
        uint8_t UpdateType;
        uint32_t dwUniqueID;
        uint64_t ullState1;
        uint64_t ullState2;
        uint8_t byFlag;
        uint32_t dwParam1;
        uint32_t dwParam2;
        uint32_t dwParam3;
        uint16_t wParam4;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterInfoUpdate(
        byte UpdateType,
        uint dwUniqueID,
        ulong ullState1,
        ulong ullState2,
        byte byFlag,
        uint dwParam1,
        uint dwParam2,
        uint dwParam3,
        ushort wParam4
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterInfoUpdate {
        pub update_type: u8,
        pub dw_unique_id: u32,
        pub ull_state1: u64,
        pub ull_state2: u64,
        pub by_flag: u8,
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub dw_param3: u32,
        pub w_param4: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterInfoUpdate struct {
        UpdateType uint8
        dwUniqueID uint32
        ullState1 uint64
        ullState2 uint64
        byFlag uint8
        dwParam1 uint32
        dwParam2 uint32
        dwParam3 uint32
        wParam4 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterInfoUpdate {
        updateType: number;
        dwUniqueID: number;
        ullState1: bigint;
        ullState2: bigint;
        byFlag: number;
        dwParam1: number;
        dwParam2: number;
        dwParam3: number;
        wParam4: number;
    }
    ```


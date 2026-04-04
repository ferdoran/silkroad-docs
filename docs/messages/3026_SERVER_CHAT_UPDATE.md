# SERVER_CHAT_UPDATE

> **Corrected name** (server RE): Was `SERVER_WEATHER` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3026` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00877340` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `updateType` | `u8` | 1 |  |
| 2 | `uniqueID` | `u32` | 4 | case(SRTypes.Chat.All) |
| 3 | `player` | `string` | var | case(SRTypes.Chat.All) → if(p == null) |
| 4 | `message` | `string` | var | case(SRTypes.Chat.All) → if(p == null) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0087738C` |
| 2 | `byIntensity` | `u8` | 1 | `0x008773A6` |
| 3 | `byWindDir` | `u8` | 1 | `0x008773B4` |
| 4 | `wDuration` | `u16` | 2 | `0x0087753F` |
| 5 | `bySpecial` | `u8` | 1 | `0x00877560` |
| 6 | `byRegionWeather` | `u8` | 1 | `0x0087756E` |

**Total size**: 7 bytes

</details>
### Structure Summary

```
  [   0] byType                         u8
  [   1] byIntensity                    u8
  [   2] byWindDir                      u8
  [   3] wDuration                      u16
  [   5] bySpecial                      u8
  [   6] byRegionWeather                u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ChatUpdate {
        uint8_t byType;
        uint8_t byIntensity;
        uint8_t byWindDir;
        uint16_t wDuration;
        uint8_t bySpecial;
        uint8_t byRegionWeather;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ChatUpdate(
        byte byType,
        byte byIntensity,
        byte byWindDir,
        ushort wDuration,
        byte bySpecial,
        byte byRegionWeather
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ChatUpdate {
        pub by_type: u8,
        pub by_intensity: u8,
        pub by_wind_dir: u8,
        pub w_duration: u16,
        pub by_special: u8,
        pub by_region_weather: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type ChatUpdate struct {
        byType uint8
        byIntensity uint8
        byWindDir uint8
        wDuration uint16
        bySpecial uint8
        byRegionWeather uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ChatUpdate {
        byType: number;
        byIntensity: number;
        byWindDir: number;
        wDuration: number;
        bySpecial: number;
        byRegionWeather: number;
    }
    ```


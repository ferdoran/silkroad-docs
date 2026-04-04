# SERVER_ENVIROMENT_WEATHER_UPDATE

> **Corrected name** (server RE): Was `SERVER_TIME_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3809` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x008A6E80` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `wheaterType` | `u8` | 1 |  |
| 2 | `wheaterIntensity` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wDay` | `u16` | 2 | `0x008A6E9E` |
| 2 | `byHour` | `u8` | 1 | `0x008A6EAE` |
| 3 | `byMinute` | `u8` | 1 | `0x008A6EBE` |

**Total size**: 4 bytes

</details>
### Structure Summary

```
  [   0] wDay                           u16
  [   2] byHour                         u8
  [   3] byMinute                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EnviromentWeatherUpdate {
        uint16_t wDay;
        uint8_t byHour;
        uint8_t byMinute;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EnviromentWeatherUpdate(
        ushort wDay,
        byte byHour,
        byte byMinute
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EnviromentWeatherUpdate {
        pub w_day: u16,
        pub by_hour: u8,
        pub by_minute: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EnviromentWeatherUpdate struct {
        wDay uint16
        byHour uint8
        byMinute uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EnviromentWeatherUpdate {
        wDay: number;
        byHour: number;
        byMinute: number;
    }
    ```


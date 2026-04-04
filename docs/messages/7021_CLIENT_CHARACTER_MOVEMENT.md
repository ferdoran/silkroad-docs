# CLIENT_CHARACTER_MOVEMENT

| Property | Value |
|----------|-------|
| Opcode | `0x7021` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `petUniqueID` | `u32` | 4 |  |
| 2 | `Movement` | `u8` | 1 |  |
| 3 | `unk` | `u8` | 1 |  |
| 4 | `region` | `u16` | 2 |  |
| 5 | `x` | `i32` | 4 |  |
| 6 | `z` | `i32` | 4 |  |
| 7 | `y` | `i32` | 4 |  |
| 8 | `x` | `i16` | 2 |  |
| 9 | `z` | `i16` | 2 |  |
| 10 | `y` | `i16` | 2 |  |


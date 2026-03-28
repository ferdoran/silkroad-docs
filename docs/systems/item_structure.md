# Item Structure (Shared Sub-Structure)

Shared binary structure used for inventory items across multiple packets including [SERVER_CHARACTER_DATA](../messages/3013_SERVER_CHARACTER_DATA.md), [SERVER_PET_DATA](../messages/30C8_SERVER_PET_DATA.md), and others.

Source: [server_binary_analysis.md](../server_binary_analysis.md) section 6.

## Rentable Info (prefix)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `RentableType` | `u32` | 4 | 0=None, 1=LimitedTime, 2=LimitedDistance, 3=Package |

### RentableType 1 — LimitedTime

| Name | Type | Size | Description |
|------|------|------|-------------|
| `CanDelete` | `u16` | 2 | Deletion flag |
| `PeriodBeginTime` | `u32` | 4 | Rental start time |
| `PeriodEndTime` | `u32` | 4 | Rental end time |

### RentableType 2 — LimitedDistance

| Name | Type | Size | Description |
|------|------|------|-------------|
| `CanDelete` | `u16` | 2 | Deletion flag |
| `CanRecharge` | `u16` | 2 | Recharge flag |
| `MeterRateTime` | `u32` | 4 | Distance meter rate |

### RentableType 3 — Package

| Name | Type | Size | Description |
|------|------|------|-------------|
| `CanDelete` | `u16` | 2 | Deletion flag |
| `CanRecharge` | `u16` | 2 | Recharge flag |
| `PeriodBeginTime` | `u32` | 4 | Rental start time |
| `PeriodEndTime` | `u32` | 4 | Rental end time |
| `PackingTime` | `u32` | 4 | Packing timestamp |

## Item Core

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `RefItemID` | `u32` | 4 | Item reference ID (determines branch) |

---

### Branch: isEquipable

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 3 | `Plus` | `u8` | 1 | Enhancement level (+1, +2, etc.) |
| 4 | `Variance` | `u64` | 8 | Random stat variance seed |
| 5 | `Durability` | `u32` | 4 | Current durability |

#### Magic Options

| Name | Type | Size | Description |
|------|------|------|-------------|
| `MagicOptionCount` | `u8` | 1 | Number of blue stats |

For each option: `u32 OptionID, u32 Value`

#### Sockets

| Name | Type | Size | Description |
|------|------|------|-------------|
| `SocketFlag` | `u8` | 1 | Always 1 |
| `SocketCount` | `u8` | 1 | Number of sockets |

For each socket: `u8 SlotType, u32 SocketID, u32 Value`

#### Advanced Elixirs

| Name | Type | Size | Description |
|------|------|------|-------------|
| `ElixirFlag` | `u8` | 1 | Always 2 |
| `ElixirCount` | `u8` | 1 | Number of advanced elixirs |

For each elixir: `u8 SlotType, u32 ElixirID, u32 Value`

---

### Branch: isCoS (Companion Scroll)

#### isPet

| Name | Type | Size | Description |
|------|------|------|-------------|
| `StateType` | `u8` | 1 | 0=NeverSummoned, 1+=Active |

If `StateType != NeverSummoned`:

| Name | Type | Size | Description |
|------|------|------|-------------|
| `ModelID` | `u32` | 4 | Pet model |
| `PetName` | `ascii` | var | Pet name |
| `PeriodEndTime` | `u32` | 4 | Only if ID4 == 2 |
| `unkByte01` | `u8` | 1 | |

#### isTransform

| Name | Type | Size | Description |
|------|------|------|-------------|
| `ModelID` | `u32` | 4 | Transform model |

#### isCube

| Name | Type | Size | Description |
|------|------|------|-------------|
| `Quantity` | `u32` | 4 | Number of cubes |

---

### Branch: isEtc

| Name | Type | Size | Description |
|------|------|------|-------------|
| `Quantity` | `u16` | 2 | Stack quantity |

If `isAlchemy && (ID4 == 1 || ID4 == 2)`:

| Name | Type | Size | Description |
|------|------|------|-------------|
| `AssimilationProbability` | `u8` | 1 | Magic/Attribute stone success rate |

If `ID3 == 14 && ID4 == 2` (Gacha card):

| Name | Type | Size | Description |
|------|------|------|-------------|
| `ParamCount` | `u8` | 1 | Number of card params |

For each param: `u32 ParamID, u32 Value`

## Full Structure Summary

```
// Rentable Info (prefix)
u32     RentableType               // 0=None, 1=LimitedTime, 2=LimitedDistance, 3=Package
if LimitedTime:
    u16     CanDelete
    u32     PeriodBeginTime
    u32     PeriodEndTime
elif LimitedDistance:
    u16     CanDelete
    u16     CanRecharge
    u32     MeterRateTime
elif Package:
    u16     CanDelete
    u16     CanRecharge
    u32     PeriodBeginTime
    u32     PeriodEndTime
    u32     PackingTime

// Item Core
u32     RefItemID

IF isEquipable:
    u8      Plus
    u64     Variance
    u32     Durability
    u8      MagicOptionCount
    for each: u32 OptionID, u32 Value
    u8      SocketFlag             // always 1
    u8      SocketCount
    for each: u8 SlotType, u32 SocketID, u32 Value
    u8      ElixirFlag             // always 2
    u8      ElixirCount
    for each: u8 SlotType, u32 ElixirID, u32 Value

ELIF isCoS:
    IF isPet:
        u8      StateType          // 0=NeverSummoned, 1+=Active
        if Active: u32 ModelID, ascii PetName, [u32 PeriodEndTime], u8 unkByte01
    ELIF isTransform:
        u32     ModelID
    ELIF isCube:
        u32     Quantity

ELIF isEtc:
    u16     Quantity
    if isAlchemy stone: u8 AssimilationProbability
    elif isGachaCard: u8 ParamCount, for each: u32 ParamID, u32 Value
```

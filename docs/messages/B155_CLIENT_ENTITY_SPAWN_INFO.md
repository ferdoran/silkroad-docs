# SERVER_ENTITY_SPAWN_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

> **Direction corrected** (server RE): The server **sends** this packet to the client;
> the "CLIENT_" prefix in the client-derived name reflects the client-side naming convention.
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB155` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x0087FE00` |
| Send site(s) | `0x509FA0`, `0x50920A` (Variant A, 7 bytes); `0x50A100`, `0x4ECCF4` (Variant B, 2 bytes) |

### Packet Variants

B155 has **two structural variants** sent from different code paths within the same `CMakeStuff_Compound` class:

---

#### Variant A — Compound Slot Spawn (7 bytes)

Sent by `method.CMakeStuff_Compound` functions at VAs `0x509FA0` and `0x50920A` when a compound crafting slot is activated.

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `SpawnType` | `u8` | 1 | Always `1` — compound slot spawn event |
| 2 | `SubType` | `u8` | 1 | Always `2` — compound slot activation phase // inferred |
| 3 | `SlotItemType` | `u8` | 1 | Low byte of compound slot's item type reference (first DWORD of slot struct); identifies the type of item in the slot |
| 4 | `UniqueID` | `u32` | 4 | Entity unique ID; from `entity->vtable[0x4e8/4]()` call on the slot's entity object |

**Structure Summary:**
```
  [0] SpawnType     u8   // constant 1
  [1] SubType       u8   // constant 2
  [2] SlotItemType  u8   // slot struct first-byte
  [3] UniqueID      u32  // entity vtable[314]()
```
Total: **7 bytes**

---

#### Variant B — Acknowledgment (2 bytes)

Sent by `method.CGObjPC.virtual_1432` (VA `0x4ECCF4`, responding to opcode `0x7155`) and `method.CMakeStuff_Compound` (VA `0x50A161`, responding to incoming state read). Sent as a simple status confirmation.

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `AckType` | `u8` | 1 | Always `1` — acknowledgment event type // inferred |
| 2 | `AckResult` | `u8` | 1 | Always `1` — success // inferred |

**Structure Summary:**
```
  [0] AckType    u8  // constant 1
  [1] AckResult  u8  // constant 1
```
Total: **2 bytes**

---

### Binary Evidence

#### Variant A — Send site `0x509FA0` / `0x50A013`

Write sizes from `eax` before each `call 0x404090`:

| Write VA | `eax` | Field | Value Source |
|----------|-------|-------|-------------|
| `0x0050A063` | 1 | SpawnType | Local byte; set to constant `1` at `0x50A05E` |
| `0x0050A074` | 1 | SubType | Local byte; set to constant `2` at `0x50A059` |
| `0x0050A085` | 1 | SlotItemType | `cl = byte ptr [*list_begin]`; read at `0x50A047` from first compound slot |
| `0x0050A096` | 4 | UniqueID | Local DWORD; initialized to `1` at `0x50A02C` (CMakeStuff_Compound context) |

Send: `mov edx, [eax + 0x27c]; push esi; call edx` at VA `0x0050A0A7`.

#### Variant A — Send site `0x50920A` (more complete entity context)

| Write VA | `eax` | Field | Value Source |
|----------|-------|-------|-------------|
| `0x0050923B` | 1 | SpawnType | Constant `1` written to local at `0x509236` |
| `0x0050924C` | 1 | SubType | Constant `2` written to local at `0x509231` |
| `0x0050925D` | 1 | SlotItemType | `dl` from `[esp+0x1c]`; set to low byte of slot's first DWORD at `0x5090CC` |
| `0x0050926E` | 4 | UniqueID | `[ebx+0x90]`; stored from `entity->vtable[0x4e8/4]()` call at `0x5090F4` |

#### Variant B — Send site `0x4ECCF4` (opcode `0x7155` response, `CGObjPC` context)

| Write VA | `eax` | Field | Value Source |
|----------|-------|-------|-------------|
| `0x004ECD15` | 1 | AckType | Constant `1` (via `CONCAT13(1, CONCAT12(1, ...))` in Ghidra output) |
| `0x004ECD26` | 1 | AckResult | Constant `1` |

#### Variant B — Send site `0x50A161` (`CMakeStuff_Compound` ack path)

| Write VA | `eax` | Field | Value Source |
|----------|-------|-------|-------------|
| `0x0050A182` | 1 | AckType | Local byte; set to constant `1` at `0x50A178` |
| `0x0050A193` | 1 | AckResult | Local byte; set to constant `1` at `0x50A17D` |

### String References

| String | Type |
|--------|------|
| `ITEM_QSP_ALL_POTION_1_01` | Debug — confirms compound crafting/inventory context |

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpawnInfoCompoundSlotSpawn {
        uint8_t SpawnType;
        uint8_t SubType;
        uint8_t SlotItemType;
        uint32_t UniqueID;
    };
    struct EntitySpawnInfoAcknowledgment {
        uint8_t AckType;
        uint8_t AckResult;
    };
    struct EntitySpawnInfo {
        std::variant<EntitySpawnInfoCompoundSlotSpawn, EntitySpawnInfoAcknowledgment> body;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public abstract record EntitySpawnInfoBody;
    public record EntitySpawnInfoCompoundSlotSpawn(byte SpawnType, byte SubType, byte SlotItemType, uint UniqueID) : EntitySpawnInfoBody;
    public record EntitySpawnInfoAcknowledgment(byte AckType, byte AckResult) : EntitySpawnInfoBody;
    public record EntitySpawnInfo(EntitySpawnInfoBody Body);
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpawnInfoCompoundSlotSpawn {
        pub spawn_type: u8,
        pub sub_type: u8,
        pub slot_item_type: u8,
        pub unique_id: u32,
    }
    pub struct EntitySpawnInfoAcknowledgment {
        pub ack_type: u8,
        pub ack_result: u8,
    }
    pub enum EntitySpawnInfoBody {
        CompoundSlotSpawn(EntitySpawnInfoCompoundSlotSpawn),
        Acknowledgment(EntitySpawnInfoAcknowledgment),
    }
    pub struct EntitySpawnInfo {
        pub body: EntitySpawnInfoBody,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpawnInfoBody interface { entitySpawnInfoBody() }
    type EntitySpawnInfoCompoundSlotSpawn struct {
        SpawnType uint8
        SubType uint8
        SlotItemType uint8
        UniqueID uint32
    }
    func (*EntitySpawnInfoCompoundSlotSpawn) entitySpawnInfoBody() {}
    type EntitySpawnInfoAcknowledgment struct {
        AckType uint8
        AckResult uint8
    }
    func (*EntitySpawnInfoAcknowledgment) entitySpawnInfoBody() {}
    type EntitySpawnInfo struct {
        Body EntitySpawnInfoBody
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    type EntitySpawnInfoBody =
        | { kind: 'CompoundSlotSpawn'; spawnType: number; subType: number; slotItemType: number; uniqueID: number }
        | { kind: 'Acknowledgment'; ackType: number; ackResult: number };
    export interface EntitySpawnInfo {
        body: EntitySpawnInfoBody;
    }
    ```


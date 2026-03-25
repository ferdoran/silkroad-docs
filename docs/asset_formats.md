# Asset File Formats

Complete reference for all binary and text file formats found within Silkroad Online's PK2 archives.

## Table of Contents

- [Overview](#overview)
- [JMXV Common Header](#jmxv-common-header)
- [JMXV Formats](#jmxv-formats)
  - [1. JMXVDDJ - Texture Container](#1-jmxvddj---texture-container)
  - [2. JMXVBMS - Binary Mesh](#2-jmxvbms---binary-mesh)
  - [3. JMXVRES - Binary Scene Resource](#3-jmxvres---binary-scene-resource)
    - [Equipment Attachment Pipeline](#equipment-attachment-pipeline)
  - [4. JMXVNVM - Navigation Mesh](#4-jmxvnvm---navigation-mesh)
  - [5. JMXVBAN - Binary Animation](#5-jmxvban---binary-animation)
  - [6. JMXVBMT - Binary Material](#6-jmxvbmt---binary-material)
  - [7. JMXVBSK - Binary Skeleton](#7-jmxvbsk---binary-skeleton)
  - [8. JMXVCPD - Character Parameter Data](#8-jmxvcpd---character-parameter-data)
  - [9. JMXVDOF - Dungeon Object File](#9-jmxvdof---dungeon-object-file)
  - [10. JMXVMFO - Map Info](#10-jmxvmfo---map-info)
  - [11. JMXVOBJI - Object Index](#11-jmxvobji---object-index-text-based)
  - [12. JMXV2DTI - 2D Tile Index](#12-jmxv2dti---2d-tile-index-text-based)
- [Non-JMXV Formats](#non-jmxv-formats)
  - [13. DDS - DirectDraw Surface](#13-dds---directdraw-surface)
  - [14. 2DT - UI Definition Template](#14-2dt---ui-definition-template)
  - [15. WAV - WAVE Audio](#15-wav---wave-audio)
  - [16. TGA - Targa Image](#16-tga---targa-image)
  - [17. TTF - TrueType Font](#17-ttf---truetype-font)
  - [18. DAT - Binary Data](#18-dat---binary-data-multiple-uses)
  - [19. Shader Source Code](#19-shader-source-code)
  - [20. TXT - Text Data Tables](#20-txt---text-data-tables)
- [Format Summary by Archive](#format-summary-by-archive)
- [See Also](#see-also)

## Overview

| Archive | Files | Unique Formats |
|---------|-------|---------------|
| Data.pk2 | ~49,467 | 18 extensions |
| Media.pk2 | ~38,348 | 8 extensions |

All proprietary formats belong to the **JMXV** (JoyMax Version) family and share a common 12-byte header prefix.

---

## JMXV Common Header

All JoyMax proprietary binary formats begin with:

```
Offset  Size  Type    Description
0x00    4     char[]  Magic: "JMXV"
0x04    4     char[]  Format ID (e.g., "BMS ", "DDJ ", "RES ")
0x08    4     char[]  Version string (e.g., "0109", "1000")
```

The format ID is left-aligned and space-padded to 4 bytes (e.g., `"BMS "`, `"DDJ "`). The two text-based formats (OBJI, 2DTI) omit the space padding and use no separator before the version.

---

## JMXV Formats

### 1. JMXVDDJ - Texture Container

**Extension**: `.ddj`
**Version**: `1000`
**Count**: 12,163 (Data.pk2) + 18,910 (Media.pk2) = 31,073 total
**Purpose**: JoyMax texture wrapper around standard DDS data.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVDDJ 1000"
0x0C    4     u32     DDS data size (bytes)
0x10    4     u32     Flags (observed: 0x03 = has mipmaps+alpha?)
0x14    ...   DDS     Standard DDS file data (starts with "DDS " magic)
```

**Hex sample**:
```
00000000: 4a4d 5856 4444 4a20 3130 3030 8840 0000  JMXVDDJ 1000.@..
00000010: 0300 0000 4444 5320 7c00 0000 0710 0000  ....DDS |.......
```

The embedded DDS at offset 0x14 is a complete, valid DDS file. To extract: skip 20 bytes and write the remainder.

**Locations**: `prim/lightmap/`, `prim/mtrl/`, `water/`, `media/icon/` (Data); `effect/`, `icon/`, `interface/`, `minimap/` (Media)

---

### 2. JMXVBMS - Binary Mesh

**Extension**: `.bms`
**Versions**: `0109` (17 files), `0110` (16,835 files)
**Count**: 16,852 (Data.pk2)
**Purpose**: 3D mesh geometry - vertices, indices, bounding volumes, optional skinning data.

#### Header & Section Table

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVBMS 0109" or "JMXVBMS 0110"
0x0C    4     u32     Offset: vertex data (Section 0)
0x10    4     u32     Offset: bone/skin data (Section 1)
0x14    4     u32     Offset: index data (Section 2)
0x18    4     u32     Offset: Section 3 (unknown, always 0?)
0x1C    4     u32     Offset: Section 4 (unknown, always 0?)
0x20    4     u32     Offset: bounding box (Section 5)
0x24    4     u32     Offset: Section 6 (unknown)
0x28    4     u32     Offset: Section 7 (0109 only; collision/extra data)
0x2C    4     u32     Offset: Section 8 (always 0 in 0110)
0x30    4     u32     Offset: tail section
0x34    4     u32     Reserved (0)
0x38    4     u32     Reserved (0)
0x3C    4     u32     Sub-mesh count (observed: 1)
0x40    4     u32     Reserved (0)
0x44    4     u32     Reserved (0)
0x48    4     u32     Mesh name length
0x4C    N     char[]  Mesh name (ASCII)
0x4C+N  4     u32     Material name length
...     M     char[]  Material name (ASCII)
...     4     u32     Unknown flags/padding
```

#### Section 0: Vertex Data

```
Offset  Size  Type    Description
+0x00   4     u32     Vertex count
+0x04   44*N  ...     Vertex array (44 bytes per vertex):
          12   float3   Position (X, Y, Z)
          12   float3   Normal (X, Y, Z)
           8   float2   Texture UV (U, V)
           4   u32      Vertex color (0xAARRGGBB or 0x00000000)
           4   u32      Extra (bone index or 0xFFFFFFFF for static)
```

Vertex stride is consistently **44 bytes** across both versions.

#### Section 1: Bone/Skinning Data

For static meshes: contains only `u32(0)` (4 bytes, empty).

For animated meshes (`_ani` suffix): contains bone references and per-vertex skinning weights.
```
+0x00   4     u32     Bone count
Per bone:
  +0x00  4     u32     Bone name length
  +0x04  N     char[]  Bone name
After bones: per-vertex weight/index data
```

#### Section 2: Index Data

```
+0x00   4     u32     Triangle count
+0x04   6*N   u16[3]  Triangle indices (3 u16 per triangle)
```

#### Section 5: Bounding Box

```
+0x00   24    float[6]  min_X, min_Y, min_Z, max_X, max_Y, max_Z
```

#### Version Differences (0109 vs 0110)

| Feature | 0109 | 0110 |
|---------|------|------|
| Section 7 | Active (extra data) | Always 0 (unused) |
| File count | 17 | 16,835 |

**Hex sample (0110)**:
```
00000000: 4a4d 5856 424d 5320 3031 3130 7000 0000  JMXVBMS 0110p...
00000010: b429 0000 b829 0000 c42d 0000 4835 0000  .)...)...-..H5..
00000020: 503d 0000 683d 0000 0000 0000 0000 0000  P=..h=..........
00000030: 6c3d 0000                                 l=..
```

**Locations**: `prim/mesh/`

---

### 3. JMXVRES - Binary Scene Resource

**Extension**: `.bsr`
**Version**: `0109`
**Count**: 5,563 (Data.pk2)
**Purpose**: Compound scene object definitions. References `.bms` meshes, `.bmt` materials, `.bsk` skeletons, and `.ban` animations by file path. Defines how meshes are grouped into parts, animation playback config, and effect/sound event bindings.

#### Header

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVRES 0109"
0x0C    32    u32[8]  Section offset table (absolute file offsets)
0x2C    20    u8[]    Reserved (zeros)
0x40    2     u16     Type1 (see table below)
0x42    2     u16     Type2 (always 2)
0x44    4     u32     resource_name_len
0x48    N     char[]  resource_name (null-terminated, padded to section start)
```

The 8 section offsets point to sections that appear in arbitrary file order. Sections are NOT stored in index order.

**Type1 values:**

| Type1 | Category | Description |
|-------|----------|-------------|
| 0 | Character | Player character base models (`res/char/`) |
| 1 | Animated | Animated objects: summons, pets, interface models |
| 2 | Building | Buildings, architectural elements |
| 3 | Interactive | Interactive/animated structures (teleporters, NPCs) |
| 4 | Nature | Static nature objects (rocks, trees) |
| 5 | Equipment | Equippable items: weapons, armor, shields, accessories |
| 6 | UI/Static | UI elements, quest markers, static decorations |

#### Section [0] - Materials

```c
struct Section0_Materials {
    u32  count;                     // number of material entries
    struct {
        u32  flags;                 // material variant index (0=normal, 1=clone, 2=champion, etc.)
        u32  path_len;
        char path[path_len];        // .bmt file path (e.g. "prim\mtrl\mob\oasis\archer.bmt")
    } entries[count];
};
```

#### Section [1] - Meshes

```c
struct Section1_Meshes {
    u32  count;                     // number of mesh entries
    struct {
        u32  path_len;
        char path[path_len];        // .bms file path
    } entries[count];
};
```

#### Section [2] - Skeleton and Attachment

```c
struct Section2_Skeleton {
    u32  count;                     // 0 or 1
    struct {
        u32  path_len;
        char path[path_len];        // .bsk file path
    } entries[count];
    u32  attach_bone_len;           // 0 if no attachment, >0 for equipable items
    char attach_bone[attach_bone_len]; // character bone name to attach to (see table)
};
```

**Attachment bone** specifies which bone on the **character skeleton** this item's root bone is parented to at runtime. Only present in Type1=5 (equipment) BSRs that have a skeleton.

| Attachment Bone | Count | Used By |
|-----------------|-------|---------|
| `Bip01 R HandMid` | 181 | Swords, blades, spears, staffs, axes (right hand) |
| `Bip01 L HandMid2` | 83 | Dual-wield left-hand weapons, two-handed staves |
| `Bip01 L Hand` | 46 | Bows, shields |
| `Bip01 Neck` | 46 | Shoulder armor, capes |
| `Bip01 Neck1` | 16 | Scarves, accessories |
| `Bip01 Spine` | 14 | Back-mounted items (balloons) |
| `Bip01 Spine1` | 14 | Wings, fairy attachments |
| `Bip01 Head` | 2 | Hats |

Armor pieces (Type1=5 without a skeleton) have `count=0` and `attach_bone_len=0`. Their meshes are skinned directly to character skeleton bones and replace body parts via the equipment slot system.

#### Section [3] - Animations

```c
struct Section3_Animations {
    u32  mesh_config;               // 0x1000 (mesh render flags)
    u32  unk;                       // always 0
    u32  anim_count;                // number of animation entries
    struct {
        u32  path_len;
        char path[path_len];        // .ban file path
    } animations[anim_count];
};
```

#### Section [4] - Mesh Parts

Groups meshes into named parts (e.g. "default"). Each part defines which mesh indices belong to it.

```c
struct Section4_MeshParts {
    u32  part_count;                // number of named parts (typically 1)
    struct {
        u32  name_len;
        char name[name_len];        // part name (e.g. "default")
        u32  mesh_count;            // number of meshes in this part
        u32  mesh_indices[mesh_count]; // indices into Section [1]
    } parts[part_count];
};
```

#### Section [5] - Animation Config

Per-part animation playback configuration. Each animation has a type ID, flags, optional sound/hit events, and speed multipliers.

```c
struct Section5_AnimConfig {
    u32  part_count;                // matches Section [4] part_count
    struct {
        u32  name_len;
        char name[name_len];        // part name (e.g. "default")
        u32  anim_config_count;     // may exceed Section [3] anim_count (includes state aliases)
        struct {
            u32  anim_type_id;      // animation state type (0=idle, 1=idle2, 2=walk, etc.)
            u32  anim_index;        // index into Section [3] animation list
            u32  event_count;       // number of hit/sound trigger events
            struct {
                u32  tick;          // trigger time in animation ticks
                u32  unk1;
                u32  unk2;
                u32  unk3;
            } events[event_count];
            u32  unk_field;         // typically 2
            f32  speed_param;       // animation speed parameter (0.0 or specific value like 21.33, 60.48)
            u32  unk2;              // 0
            u32  unk3;              // 0
            f32  walk_speed;        // walk speed multiplier (typically 1.0)
            f32  run_speed;         // run speed multiplier (typically 1.0)
        } configs[anim_config_count];
    } parts[part_count];
};
```

**Verified**: 9 u32s base per config entry + 4 u32s per event. Total section size matches exactly.

#### Section [6] - Effects and Sound Events

Complex hierarchical section containing visual effect bindings (status effects, ambient), material overrides, and per-animation sound event definitions. Uses `0xFFFFFFFF` sentinels to delimit entries.

```c
struct Section6_Effects {
    u32  named_effect_count;        // number of named effect entries (status effects, ambient)
    u32  type;                      // 0=mob/char effects, 2=static/ambient

    // Entries are delimited by 0xFFFFFFFF sentinels.
    // Named effects come in pairs: a named block + a config block.
    // After all named effects, animation-sound blocks follow.

    // Each sentinel-delimited block:
    struct EffectBlock {
        i32  sentinel;              // always -1 (0xFFFFFFFF)
        u32  name_len;              // 0 for config/sound blocks, >0 for named blocks
        char name[name_len];        // effect name (e.g. "status_bad_burn", "ambient")
        u8   config_data[];         // variable-length config (see below)
    };
};
```

**Named effect blocks** (name_len > 0): 20 bytes of fixed config follow the name.

**Status effect config blocks** (name_len = 0, following a named status effect):
- 4 u32 header fields
- u32 path_len + .efp file path (e.g. `"monster\status_bad_burn.efp"`)
- Zero padding (typically 24-28 bytes)

**Animation-sound blocks** (name_len = 0, after all named effects):
- u32 anim_sound_count (total animation-sound entries that follow)
- Per animation: part name, sound/material references, and bounding parameters
- Each references .wav file paths with event names (e.g. `"snd_walk1"`, `"snd_swing1"`, `"voc_death"`)
- Contains rendering parameters: floats for distance/volume (e.g. 10.0, 100.0)

> **Note**: Section [6] has a complex recursive structure. The above describes the overall layout; exact per-field parsing of effect config data and animation-sound blocks requires further reverse-engineering.

#### Section [7] - Bounding Box

```c
struct Section7_BBox {
    u32  unk;                       // always 0
    f32  bbox_min[3];               // min corner (x, y, z)
    f32  bbox_max[3];               // max corner (x, y, z)
    f32  bbox_min_copy[3];          // duplicate of bbox_min
    f32  bbox_max_copy[3];          // duplicate of bbox_max
    u32  unk2;                      // always 0
};
// Total: 56 bytes
```

#### Section File Order

Sections are stored in the file in a consistent order that differs from their index:

| File order | Section | Content |
|------------|---------|---------|
| 1st | [7] | Bounding box (56 bytes, immediately after header) |
| 2nd | [0] | Materials |
| 3rd | [1] | Meshes |
| 4th | [3] | Animations |
| 5th | [2] | Skeleton |
| 6th | [4] | Mesh parts |
| 7th | [5] | Animation config |
| 8th | [6] | Effects/sounds (extends to end of file) |

**Hex sample** (header):
```
00000000: 4a4d 5856 5245 5320 3031 3039 2001 0000  JMXVRES 0109 ...
00000010: 7701 0000 fc02 0000 f002 0000 0003 0000  w...............
00000020: 2703 0000 2b03 0000 9d00 0000            '...+.......
```

**Locations**: `res/` (artifact, avatar, bldg, char, cos, dun, etc.)

#### Equipment Attachment Pipeline

Equipment attaches to characters through two distinct mechanisms:

**1. Armor (skinned replacement):** Armor BSRs (Type1=5, no skeleton) have meshes skinned to the same `Bip01` bone hierarchy as the character body. When equipped, armor meshes replace character body parts. The `Slot` bitmask in `charactervisualchange.txt` controls which body parts are hidden:

| Slot | Body Part |
|------|-----------|
| `0x0002` | Chest/Mail |
| `0x0004` | Shoulder |
| `0x0008` | Gauntlet |
| `0x0010` | Pants |
| `0x0020` | Boots |
| `0x0040` | Weapon |
| `0x0080` | Shield |
| `0x0801` | Helm |

**2. Weapons/Accessories (bone attachment):** Weapon BSRs (Type1=5, with skeleton) have their own local skeleton (e.g., `Bone01`, `ai_start`, `ai_end`). The BSR's Section [2] specifies an `attach_bone` — a character skeleton bone name. At runtime, the engine parents the weapon's root bone transform to this character bone. Character animations drive the hand/body bones, which carry the attached weapon.

**3. CPD (Character Parameter Data):** `.cpd` files (JMXVCPD 0101) define static preview compositions — a character BSR plus armor BSRs. They do NOT include weapons; those are equipped dynamically by the game server. Structure: JMXV header + config fields + u32 path_count + path_count length-prefixed BSR paths (character first, then armor pieces).

---

### 4. JMXVNVM - Navigation Mesh

**Extension**: `.nvm`
**Version**: `1000`
**Count**: 5,040 (Data.pk2)
**Purpose**: Grid-based pathfinding mesh for AI and player movement. Named `nv_XXXX.nvm` where XXXX is a hex region ID.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVNVM 1000"
0x0C    4     u32     Grid/tile parameter A (varies: 0x00010000, 0x00040000, etc.)
0x10    4     u32     Grid/tile parameter B (same format as A)
0x14    ...           Variable-length navmesh data
```

The internal structure is complex and varies significantly between files (74 KB to 232 KB). The data contains:

- **Cell grid data**: Walkability flags, terrain type per cell
- **Navigation vertices**: Float coordinates defining walkable polygon edges
- **Connectivity data**: u16 indices linking adjacent cells for pathfinding
- **Region references**: Neighboring region IDs for cross-region navigation

File sizes observed: 74,643 bytes (sparse regions) to 232,418 bytes (dense regions). The format uses a mix of integer cell flags and floating-point vertex coordinates, packed without consistent alignment.

> **Note**: The NVM binary layout requires further reverse-engineering. Fields at 0x0C+ vary across files and do not follow a simple fixed-header pattern.

**Hex sample (sparse region)**:
```
00000000: 4a4d 5856 4e56 4d20 3130 3030 0000 0100  JMXVNVM 1000....
00000010: 0000 0100 0000 0000 0000 0000 0000 0000  ................
```

**Hex sample (denser region)**:
```
00000000: 4a4d 5856 4e56 4d20 3130 3030 0000 0400  JMXVNVM 1000....
00000010: 0000 0400 0000 0000 0000 0000 0000 0000  ................
00000020: 7044 0000 7044 0000 0000 0000 0070 4400  pD..pD.......pD.
```

**Locations**: `navmesh/`

---

### 5. JMXVBAN - Binary Animation

**Extension**: `.ban`
**Version**: `0102`
**Count**: 3,564 (Data.pk2)
**Purpose**: Skeletal animation data - per-bone keyframe transforms (rotation + translation).

#### Full Structure

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVBAN 0102"
0x0C    4     u32     Reserved (0)
0x10    4     u32     Reserved (0)
0x14    4     u32     Animation name length
0x18    N     char[]  Animation name (ASCII)

--- After name ---
+0x00   4     u32     Total duration (ticks, e.g. 500 = ~16.7s at 30fps)
+0x04   4     u32     Flag (observed: 30, possibly related to framerate)
+0x08   4     u32     Unknown (0 or 1)
+0x0C   4     u32     Keyframe timestamp count (K)
+0x10   4*K   u32[]   Keyframe timestamps (ascending, in ticks)

--- After timestamps ---
+0x00   4     u32     Bone count (B)

--- Per bone (repeated B times) ---
+0x00   4     u32     Bone name length
+0x04   N     char[]  Bone name (e.g. "Bip01 Spine1")
+N      4     u32     Keyframe count for this bone (matches global K)
+N+4    28*K  ...     Keyframe data array:
          16   float4   Rotation quaternion (X, Y, Z, W)
          12   float3   Position (X, Y, Z)
```

Each keyframe is **28 bytes**: a unit quaternion for rotation and a 3D vector for translation. Timestamps are shared across all bones (every bone has the same number of keyframes).

**Hex sample**:
```
00000000: 4a4d 5856 4241 4e20 3031 3032 0000 0000  JMXVBAN 0102....
00000010: 0000 0000 1200 0000 7275 696e 5f74 616b  ........ruin_tak
00000020: 6c61 5f65 6469 6d6d 7531                  la_edimmu1
```

**Verified**: Parser consumes 100% of file bytes (0 remaining) across all tested samples.

**Locations**: `prim/ani/`

---

### 6. JMXVBMT - Binary Material

**Extension**: `.bmt`
**Version**: `0102`
**Count**: 3,133 (Data.pk2)
**Purpose**: Material definitions - color properties, shininess, texture references.

#### Full Structure

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVBMT 0102"
0x0C    4     u32     Material count (M)

--- Per material (repeated M times) ---
+0x00   4     u32     Material name length
+0x04   N     char[]  Material name (ASCII)
+N      16    float4  Diffuse color (R, G, B, A)
+N+16   16    float4  Specular color (R, G, B, A)
+N+32   16    float4  Ambient color (R, G, B, A)
+N+48   16    float4  Emissive color (R, G, B, A)
+N+64   4     float   Shininess (specular power, e.g. 0.0)
+N+68   4     u32     Flags (e.g. 0x140, 0x40 - render state bitfield)
+N+72   4     u32     Texture filename length (0 = no texture)
+N+76   T     char[]  Texture filename (e.g. "cj_rich_wall01.ddj")
+N+76+T 4     float   Absorb/opacity (observed: always 1.0)
+N+80+T 1     u8      Flag1 (e.g. 0x18 when textured, 0x00 when not)
+N+81+T 2     u16     Flag2 (observed: 0x0000)
```

All color values are IEEE 754 floats in [0.0, 1.0] range. Common diffuse/specular values: 0.588 (0x3F16872B), ambient: 0.9 (0x3F666666).

**Verified**: Parser consumes 100% of file bytes across 1-material and 2-material files.

**Hex sample**:
```
00000000: 4a4d 5856 424d 5420 3031 3032 0100 0000  JMXVBMT 0102....
00000010: 0e00 0000 775f 6364 5f72 6f63 6b5f 4c5f  ....w_cd_rock_L_
00000020: 3031 2b87 163f 2b87 163f 2b87 163f 0000  01+..?+..?+..?..
```

**Locations**: `prim/mtrl/`

---

### 7. JMXVBSK - Binary Skeleton

**Extension**: `.bsk`
**Version**: `0101`
**Count**: 810 (Data.pk2)
**Purpose**: Bone hierarchy with bind-pose, model-space, and inverse-bind transforms.

#### Full Structure

**Note**: This format uses **unaligned reads** - fields are NOT padded to 4-byte boundaries.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVBSK 0101"
0x0C    4     u32     Bone count (e.g. 38)

--- Root bone (bone 0) ---
+0x00   1     u8      Flag (0)
+0x01   4     u32     Root bone name length (unaligned!)
+0x05   N     char[]  Root bone name (e.g. "Bip01")
+0x05+N 4     u32     Padding (0x00000000)
+0x09+N 84    ...     Transform data (see below)

--- Non-root bones (bones 1..count-1) ---
+0x00   4     u32     Linked name count (L):
                        L=1: just this bone
                        L>1: this bone + L-1 related bones (L/R pairs, etc.)
                        L=0: bone was pre-defined in a previous L>1 entry

Per linked name (L times, or 0 if L=0):
  +0x00  4     u32     Name length
  +0x04  N     char[]  Bone name

+0x00   1     u8      Flag (0)
+0x01   4     u32     Attachment bone name length
+0x05   N     char[]  Attachment bone name (same as bone name, or group ref)
+0x05+N 4     u32     Parent bone name length
+0x09+N M     char[]  Parent bone name
+0x09+N+M 84  ...     Transform data

--- Footer ---
12 bytes padding (zeros)
```

#### Transform Data (84 bytes per non-root bone, 88 for root)

Each bone stores **3 transforms** of 28 bytes each (4-float quaternion + 3-float position):

```
Bytes   Type    Description
0-27    7f      Local transform:     quat(X,Y,Z,W) + pos(X,Y,Z)
28-55   7f      Model-space transform: quat(X,Y,Z,W) + pos(X,Y,Z)
56-83   7f      Inverse bind-pose:   quat(X,Y,Z,W) + pos(X,Y,Z)
```

The root bone has 4 extra zero-bytes before its transforms (88 bytes total).

#### Linked Bones (L > 1)

Bones with symmetrical counterparts (e.g., L/R limbs) are grouped. A single entry with `linked_count=3` defines three bones at once:

```
Example: L=3 names = ["Bip01 L Thigh", "Bip01 R Thigh", "Spine_Base"]
```

The grouped bones each get their own entry later (with `linked_count=0`) to store individual transforms.

**Verified**: Full parse of 38-bone skeleton (chinaman_skel.bsk) consumes all bytes except 12-byte footer.

Bone names follow the 3ds Max Biped convention (e.g., `Bip01`, `Bip01 Spine`, `Bip01 L Hand`).

**Hex sample**:
```
00000000: 4a4d 5856 4253 4b20 3031 3031 2600 0000  JMXVBSK 0101&...
00000010: 0005 0000 0042 6970 3031 0000 0000 0000  .....Bip01......
```

**Locations**: `prim/skel/`

---

### 8. JMXVCPD - Character Parameter Data

**Extension**: `.cpd`
**Version**: `0101`
**Count**: 70 (Data.pk2)
**Purpose**: Character model composition - references body part `.bsr` files for avatar assembly.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVCPD 0101"
0x0C    4     u32     Part reference offset / count
0x10    4     u32     Data section offset / count
0x14    ...           Part references (file path strings to .bsr files)
```

**Hex sample**:
```
00000000: 4a4d 5856 4350 4420 3031 3031 3e00 0000  JMXVCPD 0101>...
00000010: 4200 0000 0000 0000 0000 0000 0000 0000  B...............
```

**Locations**: `compound/char/`, `compound/particle/`, `compound/struct/`

---

### 9. JMXVDOF - Dungeon Object File

**Extension**: `.dof`
**Version**: `0101`
**Count**: 21 (Data.pk2)
**Purpose**: Dungeon layout - object placement and spatial data.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVDOF 0101"
0x0C    4     u32     Section offset 0
0x10    ...   u32[]   Additional section offsets
```

The offset table structure is similar to BMS/BSR formats. Contains references to `.bsr` resource files for dungeon objects.

**Hex sample**:
```
00000000: 4a4d 5856 444f 4620 3031 3031 7400 0000  JMXVDOF 0101t...
00000010: 376f 0200 83e5 0100 7b71 0200 4f71 0200  7o......{q..Oq..
```

**Locations**: `dungeon/`

---

### 10. JMXVMFO - Map Info

**Extension**: `.mfo`
**Version**: `1000`
**Count**: 1 (Data.pk2)
**Purpose**: Region/world metadata for the map system.

```
Offset  Size  Type    Description
0x00    12    char[]  Header: "JMXVMFO 1000"
0x0C    4     u32     Flags or data size (observed: 0x00800100)
0x10    ...           Region metadata (mostly zero-padded)
```

**Hex sample**:
```
00000000: 4a4d 5856 4d46 4f20 3130 3030 0001 8000  JMXVMFO 1000....
```

**Locations**: `navmesh/`

---

### 11. JMXVOBJI - Object Index (text-based)

**Extension**: `.ifo`
**Version**: `1000`
**Count**: 3 of 4 `.ifo` files (Data.pk2)
**Purpose**: Text-based object placement lists for world regions.

```
Line 1:  "JMXVOBJI1000"       (no space before version)
Line 2:  <entry_count>
Line 3+: <hex_id> <hex_flags> <region_x> <region_y> <float_x> <float_y> <float_z> <float_yaw> "<object_name>"
```

**Sample**:
```
JMXVOBJI1000
189
0x7de41001 0x00000000 228 125 0x44c4f380 0x44452cb2 0x4282d487 0x3fcad559 "POS_STRUCTURE_GOD_BIG_GATE_TOGUI_1"
```

Coordinates are stored as hex-encoded IEEE 754 floats. Region X/Y are integer grid coordinates.

**Locations**: `navmesh/`

---

### 12. JMXV2DTI - 2D Tile Index (text-based)

**Extension**: `.ifo`
**Version**: `1001`
**Count**: 1 of 4 `.ifo` files (Data.pk2)
**Purpose**: 2D terrain tile definitions mapping tile IDs to texture files.

```
Line 1:  "JMXV2DTI1001"       (no space before version)
Line 2:  <entry_count>
Line 3+: <tile_index> <hex_flags> "<tile_class>" "<texture_filename.ddj>"
```

**Sample**:
```
JMXV2DTI1001
603
00000 0x00000000 "CJfild" "c_dust_fld_01.ddj"
00001 0x00000000 "CJfild" "c_dust_fld_02.ddj"
```

**Locations**: `navmesh/`

---

## Non-JMXV Formats

### 13. DDS - DirectDraw Surface

**Extension**: `.dds`
**Magic**: `DDS ` (0x44445320)
**Count**: 18,902 (Media.pk2 only)
**Purpose**: Standard Microsoft DirectDraw Surface texture format. Used alongside `.ddj` files in Media.pk2 (DDJ wraps DDS; here they appear unwrapped).

```
Offset  Size  Type    Description
0x00    4     char[]  Magic: "DDS "
0x04    4     u32     Header size (always 124 = 0x7C)
0x08    4     u32     Flags
0x0C    4     u32     Height
0x10    4     u32     Width
...
```

Standard format; see Microsoft DDS documentation.

**Locations**: `effect/`, `icon/`, `interface/`, `minimap/` (Media)

---

### 14. 2DT - UI Definition Template

**Extension**: `.2dt`
**Count**: 42 (Media.pk2)
**Purpose**: UI widget definitions for the game interface. No JMXV header.

```
Offset  Size  Type    Description
0x00    4     u32     Header/data size (e.g., 0x48 = 72)
0x04    64    char[]  Class name, null-padded (e.g., "CNIFEnchantWnd")
0x44    ...           Resource path strings (e.g., "interface\frame\mframe_wnd_")
                      followed by widget tree data
```

**Hex sample**:
```
00000000: 4800 0000 434e 4946 456e 6368 616e 7457  H...CNIFEnchantW
00000010: 6e64 0000 0000 0000 0000 0000 0000 0000  nd..............
...
00000040: 0000 0000 696e 7465 7266 6163 655c 6672  ....interface\fr
00000050: 616d 655c 6d66 7261 6d65 5f77 6e64 5f00  ame\mframe_wnd_.
```

Class names correspond to C++ UI widget classes (e.g., `CNIFEnchantWnd`, `CNIFInventory`).

**Locations**: `interface/` (Media)

---

### 15. WAV - WAVE Audio

**Extension**: `.wav`
**Magic**: `RIFF....WAVE`
**Count**: 2,159 (Data.pk2)
**Purpose**: Standard WAVE audio files for sound effects.

Standard RIFF container format. No modifications from the standard.

**Locations**: `prim/snd/`

---

### 16. TGA - Targa Image

**Extension**: `.tga`
**Count**: 3 (Data.pk2) + 3 (Media.pk2) = 6 total
**Purpose**: Uncompressed true-color images.

Standard TGA format (image type 2 = uncompressed RGB). 32x32 resolution observed.

**Locations**: Various

---

### 17. TTF - TrueType Font

**Extension**: `.ttf`
**Magic**: `0x00010000`
**Count**: 3 (Media.pk2)
**Purpose**: Standard TrueType font files for in-game text rendering.

**Locations**: `fonts/` (Media)

---

### 18. DAT - Binary Data (multiple uses)

**Extension**: `.dat`
**Count**: 18 (Data.pk2) + 53 (Media.pk2) = 71 total

This extension is used for two unrelated formats:

#### Data.pk2: AI Navigation Data
Named `ainavdata_XXXXX.dat`. Proprietary binary format (no JMXV header). Contains AI pathfinding waypoint data.

```
Offset  Size  Type    Description
0x00    ...           Binary navigation graph data (no magic/header)
```

**Locations**: `navmesh/`

#### Media.pk2: BMP Images (Launcher UI)
Standard Windows Bitmap files used for launcher UI assets.

```
Offset  Size  Type    Description
0x00    2     char[]  Magic: "BM"
0x02    4     u32     File size
0x06    4     u32     Reserved
0x0A    4     u32     Pixel data offset
0x0E    ...           DIB header + pixel data
```

**Hex sample**:
```
00000000: 424d 7823 0000 0000 0000 3204 0000 2800  BMx#......2...(.
```

8-bit indexed color observed (256-color palette).

**Locations**: `launcher/`, `launcher_europe/` (Media)

---

### 19. Shader Source Code

**Extensions**: `.c` (38 files), `.psh` (14 files), `.vsh` (8 files)
**Count**: 60 total (Data.pk2)
**Purpose**: DirectX 8/9 shader source code in plain text.

| Extension | Content | Shader Model |
|-----------|---------|-------------|
| `.c` | Vertex shader source | `vs.1.1` (DirectX 8 assembly) |
| `.vsh` | Vertex shader source | `vs.1.1` / HLSL comments |
| `.psh` | Pixel shader source | `ps.1.4` (DirectX 8 assembly) |

All files are plain ASCII text. The `.c` files are not C source code despite the extension - they contain DirectX vertex shader assembly.

**Sample (.c)**:
```
vs.1.1
;------------------------------------------------------------------------------
; v0 = position
```

**Sample (.psh)**:
```
; Terrain Pixel shader with Scattering
; (c) 2002 Nathaniel Hoffman, Kenneth J. Mitchell and Arcot J. Preetham
ps.1.4
```

**Locations**: `shader/`, `shader_maptool/`

---

### 20. TXT - Text Data Tables

**Extension**: `.txt`
**Count**: 3 (Data.pk2) + 434 (Media.pk2) = 437 total

#### Data.pk2: Plain ASCII
Configuration files (`mapinfo.txt`, `dungeoninfo.txt`, `regioninfo.txt`).

#### Media.pk2: UTF-16LE with BOM
Tab-separated data tables for game data (items, skills, quests, etc.). Files begin with UTF-16LE BOM (`0xFF 0xFE`).

```
Offset  Size  Type    Description
0x00    2     u16     BOM: 0xFFFE (UTF-16LE byte order mark)
0x02    ...   u16[]   UTF-16LE encoded text, tab-separated columns
```

**Hex sample**:
```
00000000: fffe 2300 7300 6500 6300 7400 6900 6f00  ..#.s.e.c.t.i.o.
```

**Locations**: `navmesh/`, `dungeon/`, `shader/` (Data); `server_dep/`, `script/` (Media)

---

## Format Summary by Archive

### Data.pk2

| Extension | Count | Format | Versions |
|-----------|-------|--------|----------|
| `.bms` | 16,852 | JMXVBMS | 0109, 0110 |
| `.ddj` | 12,163 | JMXVDDJ | 1000 |
| `.bsr` | 5,563 | JMXVRES | 0109 |
| `.nvm` | 5,040 | JMXVNVM | 1000 |
| `.ban` | 3,564 | JMXVBAN | 0102 |
| `.bmt` | 3,133 | JMXVBMT | 0102 |
| `.wav` | 2,159 | RIFF WAVE | - |
| `.bsk` | 810 | JMXVBSK | 0101 |
| `.cpd` | 70 | JMXVCPD | 0101 |
| `.c` | 38 | VS assembly (text) | - |
| `.dof` | 21 | JMXVDOF | 0101 |
| `.dat` | 18 | AI nav data (binary) | - |
| `.psh` | 14 | PS assembly (text) | - |
| `.vsh` | 8 | VS assembly (text) | - |
| `.ifo` | 4 | JMXVOBJI / JMXV2DTI | 1000 / 1001 |
| `.txt` | 3 | Plain text | - |
| `.tga` | 3 | Targa image | - |
| `.mfo` | 1 | JMXVMFO | 1000 |

### Media.pk2

| Extension | Count | Format | Versions |
|-----------|-------|--------|----------|
| `.ddj` | 18,910 | JMXVDDJ | 1000 |
| `.dds` | 18,902 | DirectDraw Surface | - |
| `.txt` | 434 | UTF-16LE text | - |
| `.dat` | 53 | BMP image | - |
| `.2dt` | 42 | UI Definition | - |
| `.tga` | 3 | Targa image | - |
| `.ttf` | 3 | TrueType font | - |

### Media.pk2 Directory Structure

```
Media/
  config/           - Configuration
  cursor/           - Mouse cursor graphics
  effect/           - Visual effect textures
  fonts/            - TrueType fonts
  icon/             - Item/skill icons (32x32)
  icon64/           - Large icons (64x64)
  interface/        - UI widget definitions (.2dt) and textures
  launcher/         - Launcher UI assets (BMP as .dat)
  launcher_europe/  - EU launcher variant
  minimap/          - Minimap tiles
  minimap_d/        - Dungeon minimap tiles
  res_ui/           - UI resource textures
  resinfo/          - Resource info
  script/           - Game data tables (.txt)
  server_dep/       - Server-dependent data tables
```

### Data.pk2 Directory Structure

```
Data/
  compound/         - Compound object definitions (.cpd)
    char/           - Character compositions
    particle/       - Particle compositions
    struct/         - Structure compositions
  dungeon/          - Dungeon definitions (.dof)
    asiam/          - Asian map dungeons
    china/          - Chinese map dungeons
    property/       - Dungeon properties
    wchina/         - Western China dungeons
  media/            - Icon textures (.ddj)
  navmesh/          - Navigation mesh (.nvm), AI data (.dat), map info
  prim/             - Primitive assets
    ani/            - Animations (.ban)
    lightmap/       - Lightmap textures (.ddj)
    mesh/           - 3D meshes (.bms)
    mtrl/           - Materials (.bmt, .ddj)
    skel/           - Skeletons (.bsk)
    snd/            - Sound effects (.wav)
  res/              - Scene resources (.bsr)
    artifact/       - Artifact objects
    avatar/         - Player avatar parts
    bldg/           - Buildings
    char/           - Character models
    cos/            - Costume objects
    dun/            - Dungeon objects
    etc/            - Miscellaneous
    interface/      - Interface objects
    item/           - Item models
    mob/            - Monster models
    nature/         - Nature objects (trees, rocks)
    npc/            - NPC models
    quest/          - Quest objects
  shader/           - Shader source code (.c, .vsh, .psh)
  shader_maptool/   - MapTool shader variants
  water/            - Water effect textures (.ddj)
```

---

## See Also

- [PK2 Archive Format](pk2_format.md) - Container format documentation
- [Character & Equipment Rendering](character_rendering.md) - How characters are assembled and rendered
- [Terrain & World Rendering](terrain_rendering.md) - Terrain geometry, texturing, shaders, and world structure
- [Network Protocol](network_protocol.md) - Network packet format, handshake, and encryption

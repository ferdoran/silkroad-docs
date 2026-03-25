# Character & Equipment Rendering

How Silkroad Online assembles and renders characters with equipped items.

## Table of Contents

- [Overview](#overview)
- [Character Model Assembly](#character-model-assembly)
  - [Base Character](#base-character)
  - [Skeleton Hierarchy](#skeleton-hierarchy)
  - [Body Part Meshes](#body-part-meshes)
- [Equipment Attachment](#equipment-attachment)
  - [Armor (Skinned Replacement)](#armor-skinned-replacement)
  - [Weapons and Accessories (Bone Attachment)](#weapons-and-accessories-bone-attachment)
  - [Attachment Bone Reference](#attachment-bone-reference)
  - [Slot Bitmask Reference](#slot-bitmask-reference)
- [Rendering Pipeline](#rendering-pipeline)
  - [Asset Loading](#asset-loading)
  - [Skeleton and Skinning](#skeleton-and-skinning)
  - [Materials and Textures](#materials-and-textures)
  - [Animation Playback](#animation-playback)
  - [Draw Order and Compositing](#draw-order-and-compositing)
- [File Reference](#file-reference)

## Overview

A rendered character in Silkroad Online is a composite of multiple independent assets:

```
Character BSR (res/char/)
  ├── Skeleton (.bsk) ─── shared by all meshes
  ├── Body meshes (.bms) ─── face, hair, torso, arms, legs
  ├── Materials (.bmt) ─── per-mesh material properties
  ├── Textures (.ddj) ─── DDS textures wrapped in JMXV container
  └── Animations (.ban) ─── weapon-type-specific animation sets

+ Armor BSRs (res/item/*/man_item/ or woman_item/)
  └── Replacement meshes (.bms) ─── skinned to same skeleton

+ Weapon BSR (res/item/*/weapon/)
  ├── Weapon skeleton (.bsk) ─── local bone hierarchy
  ├── Weapon mesh (.bms) ─── geometry
  └── attach_bone reference ─── parent to character bone
```

## Character Model Assembly

### Base Character

Each character type has a BSR file (e.g. `chinaman_warrior.bsr`) that defines:

| BSR Section | Content |
|-------------|---------|
| [0] Materials | 1 `.bmt` file (body + hair materials) |
| [1] Meshes | 9 `.bms` files (body parts + face + hair) |
| [2] Skeleton | 1 `.bsk` file (shared skeleton) |
| [3] Animations | ~160 `.ban` files (all weapon types) |
| [4] Parts | 1 "default" part grouping all 9 meshes |
| [5] Anim config | Per-animation type/speed/event bindings |
| [6] Effects | Status effects, ambient, per-animation sound events |
| [7] Bounding box | AABB for frustum culling |

The BSR `Type1` field is `0` for player characters.

### Skeleton Hierarchy

All characters (Chinese and European, male and female) share the **same skeleton**: `europeman_skel.bsk` with 43 bones based on the 3ds Max Biped rig:

```
Bip01 (root)
├── Bip01 Pelvis
│   ├── Bip01 Spine
│   │   ├── Spine_Base
│   │   └── Bip01 Spine1
│   │       ├── Bip01 Neck
│   │       │   ├── Bip01 Neck1
│   │       │   │   └── Bip01 Head
│   │       │   ├── cloak01 → cloak02 → cloak03 → cloak04
│   │       │   └── (cloak chain)
│   │       ├── Bip01 L Clavicle
│   │       │   └── Bip01 L UpperArm → L Forearm → L Hand
│   │       │       ├── Bip01 L HandMid / L HandMid2
│   │       │       └── Bip01 L Finger{0,1,2} → L Finger{01,11,21}
│   │       └── Bip01 R Clavicle
│   │           └── Bip01 R UpperArm → R Forearm → R Hand
│   │               ├── Bip01 R HandMid
│   │               └── Bip01 R Finger{0,1,2} → R Finger{01,11,21}
│   ├── Bip01 L Thigh → L Calf → L Foot → L Toe0
│   └── Bip01 R Thigh → R Calf → R Foot → R Toe0
```

### Body Part Meshes

The character body is split into 7 generic meshes plus 2 character-specific meshes:

| Mesh | Skeleton Bones Used | Replaceable By |
|------|-------------------|----------------|
| `man_torso_upper.bms` | Spine1, L/R Clavicle, L/R UpperArm | Chest armor |
| `man_torso_lower.bms` | Spine1, Spine, Pelvis | Chest armor |
| `man_arm_upper.bms` | L/R UpperArm, L/R Forearm, Clavicles | Shoulder armor |
| `man_arm_lower.bms` | L/R Forearm, L/R Hand, all Fingers | Gauntlet |
| `man_thigh.bms` | L/R Thigh, Pelvis, Spine, L/R Calf | Pants |
| `man_calf.bms` | L/R Calf, L/R Foot, L/R Toe0 | Boots |
| `man_pelvis.bms` | Pelvis, Spine, L/R Thigh | Pants |
| `*_face.bms` | Head, Neck1, Clavicles, Spine1 | Helm (hidden) |
| `*_hair.bms` | Head | Helm (hidden) |

Generic body meshes are shared across all character types of the same gender. Only face and hair meshes differ per character appearance.

## Equipment Attachment

Equipment uses two fundamentally different attachment mechanisms depending on whether the item has its own skeleton.

### Armor (Skinned Replacement)

Armor pieces (chest, pants, boots, gloves, shoulders, helm) have **no skeleton of their own**. Their meshes are skinned to the **same `Bip01` bones** as the character body meshes they replace.

**How it works:**

1. Load the armor BSR → get the armor `.bms` mesh
2. The armor mesh references the same character bones (e.g. `Bip01 Spine1`, `Bip01 L Clavicle`)
3. Hide the character body mesh(es) for the corresponding slot (using the `Slot` bitmask)
4. Render the armor mesh using the character's skeleton transforms

```
Before:  character body mesh ──skinned to──> Bip01 bones
After:   armor mesh ──────────skinned to──> Bip01 bones (same!)
         character body mesh ──hidden──
```

The armor mesh simply "replaces" the body geometry while using identical bone transforms. No coordinate transformation or attachment logic is needed — the armor vertices are already authored in the character skeleton's bone space.

### Weapons and Accessories (Bone Attachment)

Weapons, shields, wings, and back-mounted items have their **own skeleton** (typically just 1-3 bones like `Bone01`, `ai_start`, `ai_end`). They cannot be skinned to the character skeleton because they are rigid or semi-rigid objects.

**How it works:**

1. Load the weapon BSR → get the weapon `.bms`, `.bsk`, and the `attach_bone` name from Section [2]
2. Look up the named bone in the **character** skeleton (e.g. `Bip01 R HandMid`)
3. Each frame, compute the character bone's world-space transform from the current animation
4. Parent the weapon's root bone transform to the character bone's world transform
5. Render the weapon mesh using the combined transform

```
Character skeleton
  └── Bip01 R HandMid (world transform from animation)
        └── Weapon root bone (parented to HandMid)
              └── Weapon mesh vertices (in weapon-local space)
```

**Pseudocode:**

```
weapon_world_transform = character_bone_transforms[attach_bone] * weapon_local_transform
for each vertex in weapon_mesh:
    world_pos = weapon_world_transform * vertex.position
```

### Attachment Bone Reference

| Attachment Bone | Items | Description |
|-----------------|-------|-------------|
| `Bip01 R HandMid` | 181 | Right-hand weapons: swords, blades, spears, staffs, axes |
| `Bip01 L HandMid2` | 83 | Left-hand weapons for dual-wield, two-handed staves |
| `Bip01 L Hand` | 46 | Bows (held in left hand), shields |
| `Bip01 Neck` | 46 | Shoulder armor pieces, capes |
| `Bip01 Neck1` | 16 | Scarves, neck accessories |
| `Bip01 Spine` | 14 | Back-mounted items (event balloons) |
| `Bip01 Spine1` | 14 | Wings, fairy costume attachments |
| `Bip01 Head` | 2 | Event hats (Santa hat) |

### Slot Bitmask Reference

The `charactervisualchange.txt` config file defines which body parts each equipment slot hides:

| Slot Bitmask | Equipment Type | Body Parts Hidden |
|-------------|----------------|-------------------|
| `0x0002` | Chest / Mail | torso_upper, torso_lower |
| `0x0004` | Shoulder guard | arm_upper |
| `0x0008` | Gauntlet | arm_lower |
| `0x0010` | Pants | thigh, pelvis |
| `0x0020` | Boots | calf |
| `0x0040` | Weapon | (none — weapon is additive) |
| `0x0080` | Shield | (none — shield is additive) |
| `0x0801` | Helm | face, hair |

Weapons and shields are **additive** — they don't hide any body mesh; they add geometry via bone attachment.

## Rendering Pipeline

### Asset Loading

To render a fully equipped character, load assets in this order:

1. **Character BSR** → parse all 8 sections to get file paths
2. **Skeleton BSK** → build bone hierarchy with rest-pose transforms
3. **Body meshes BMS** → load vertex/index buffers for each body part
4. **Material BMT** → load material properties (diffuse, specular, ambient, emissive, shininess)
5. **Textures DDJ** → strip 20-byte JMXV header, load inner DDS data
6. **Equipment BSRs** → load armor/weapon meshes as needed
7. **Animations BAN** → load keyframe data for the active animation set

### Skeleton and Skinning

**Vertex format** (44 bytes per vertex in BMS Section [0]):

```
Offset  Size  Type     Description
0x00    12    float[3] Position (x, y, z)
0x0C    12    float[3] Normal (x, y, z)
0x18    8     float[2] UV coordinates (u, v)
0x20    4     u8[4]    Bone indices (into Section [1] bone list)
0x24    4     u8[4]    Bone weights (see below)
0x28    4     u32      Reserved (always 0)
```

**Bone weight encoding:**
- `0xFFFFFFFF` = single-bone binding (weight 1.0 to `bone_indices[0]`)
- Otherwise: `weights[0]` is a `u8` value (0-255) encoding the blend weight for the secondary bone. The primary bone gets `1.0 - weights[0]/255.0`

**Skinning pseudocode:**

```
for each vertex:
    if bone_weights == 0xFFFFFFFF:
        // Single bone
        skinned_pos = bone_transforms[bone_indices[0]] * vertex.position
    else:
        // Two-bone blend
        w1 = bone_weights[0] / 255.0
        w0 = 1.0 - w1
        skinned_pos = w0 * bone_transforms[bone_indices[0]] * vertex.position
                    + w1 * bone_transforms[bone_indices[1]] * vertex.position
```

**BSK transforms** store 3 transforms per bone (84 bytes = 3 x 28):
- Each transform is a **quaternion** (float[4]) + **position** (float[3]) = 28 bytes
- Transform 1: local-space (relative to parent)
- Transform 2: model-space (absolute)
- Transform 3: inverse bind pose (for skinning)

To skin vertices, compute `bone_world = animation_transform * inverse_bind_pose` per bone.

### Materials and Textures

Each mesh references a material name that maps to an entry in the `.bmt` file:

```
Material properties:
  - Diffuse color:  float[4] RGBA
  - Ambient color:  float[4] RGBA
  - Specular color: float[4] RGBA
  - Emissive color: float[4] RGBA
  - Shininess:      float (specular power)
  - Flags:          u32 (render state bits)
  - Texture path:   .ddj file reference
```

**DDJ textures** are DDS files with a 20-byte JMXV header prepended. To load:
1. Skip 20 bytes (12-byte JMXV magic + u32 size + u32 flags)
2. Read the remaining data as a standard DDS file
3. Common formats: DXT1 (opaque), DXT3/DXT5 (alpha), uncompressed BGRA

**Material flags** (observed values):
- `0x0340`: Standard opaque material
- `0x0341`: Material with alpha test (hair, foliage)
- Bit patterns suggest: alpha test enable, two-sided rendering, blend mode

### Animation Playback

Character animations are selected based on the equipped weapon type. The BSR Section [5] maps `anim_type_id` values to animation indices:

| Type ID | Animation State |
|---------|----------------|
| 0 | Idle (stand) |
| 1 | Idle variant 2 |
| 2 | Walk |
| 3 | Run |
| 4-5 | Attack 1-2 |
| 7 | Die |
| 9 | Down wait |
| 16+ | Skills, damage, etc. |

The character BSR includes separate animation sets per weapon type (spear, bow, sword, etc.). The active animation set is selected based on the currently equipped weapon.

**BAN keyframe interpolation:**
- Each BAN file stores `keyframe_count` timestamps (u32 ticks) followed by per-bone transforms at each keyframe
- Each keyframe transform is quaternion (float[4]) + position (float[3]) = 28 bytes
- Interpolate between keyframes using spherical linear interpolation (slerp) for quaternions and linear interpolation (lerp) for positions
- Animation speed is modulated by the `walk_speed` / `run_speed` multipliers from BSR Section [5]

### Draw Order and Compositing

Suggested rendering order for a fully equipped character:

1. **Compute skeleton pose**: Evaluate current animation BAN keyframes → compute world-space bone transforms
2. **Weapon attachment**: Copy the `attach_bone` world transform as the weapon root transform
3. **Draw body meshes**: For each body part not hidden by equipment slots:
   - Bind the body material/texture
   - Upload bone matrices for this mesh's bone subset
   - Draw the skinned mesh
4. **Draw armor meshes**: For each equipped armor piece:
   - Bind the armor material/texture
   - Upload bone matrices (same skeleton, armor uses same bone names)
   - Draw the skinned armor mesh
5. **Draw weapon mesh**:
   - Bind the weapon material/texture
   - Upload the weapon's parent transform (character bone × weapon local)
   - Draw the weapon mesh
6. **Draw effects**: Evaluate Section [6] effect bindings for status effects, hit particles, sound triggers

**Alpha-tested materials** (hair, capes) should be drawn after opaque geometry. Check `BMT.flags` bit 0 for alpha-test enable.

## File Reference

| File | Format | Documentation |
|------|--------|---------------|
| `.bsr` | JMXVRES 0109 | [Asset Formats: BSR](asset_formats.md#3-jmxvres---binary-scene-resource) |
| `.bms` | JMXVBMS 0109/0110 | [Asset Formats: BMS](asset_formats.md#2-jmxvbms---binary-mesh) |
| `.bsk` | JMXVBSK 0101 | [Asset Formats: BSK](asset_formats.md#7-jmxvbsk---binary-skeleton) |
| `.ban` | JMXVBAN 0102 | [Asset Formats: BAN](asset_formats.md#5-jmxvban---binary-animation) |
| `.bmt` | JMXVBMT 0102 | [Asset Formats: BMT](asset_formats.md#6-jmxvbmt---binary-material) |
| `.ddj` | JMXVDDJ 1000 | [Asset Formats: DDJ](asset_formats.md#1-jmxvddj---texture-container) |
| `.cpd` | JMXVCPD 0101 | [Asset Formats: CPD](asset_formats.md#8-jmxvcpd---character-parameter-data) |
| `.pk2` | PK2 Archive | [PK2 Format](pk2_format.md) |
| `charactervisualchange.txt` | TSV | Media.pk2 `server_dep/silkroad/textdata/` |

## See Also

- [Asset File Formats](asset_formats.md) - Complete reference for all file formats inside PK2 archives
- [PK2 Format](pk2_format.md) - PK2 archive structure and encryption
- [Terrain & World Rendering](terrain_rendering.md) - Terrain geometry, texturing, shaders, and world structure
- [Network Protocol](network_protocol.md) - Network packet format, handshake, and encryption

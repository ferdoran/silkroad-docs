# Terrain & World Rendering

How Silkroad Online constructs, textures, and renders its game world terrain.

## Table of Contents

- [Overview](#overview)
- [World Grid System](#world-grid-system)
  - [Region Coordinates](#region-coordinates)
  - [Region Info](#region-info)
  - [Map Info (MFO)](#map-info-mfo)
- [Terrain Geometry](#terrain-geometry)
  - [Navigation Mesh (NVM)](#navigation-mesh-nvm)
  - [NVM File Structure](#nvm-file-structure)
  - [Terrain Grid Construction](#terrain-grid-construction)
- [Terrain Texturing](#terrain-texturing)
  - [Tile Index (tile2d.ifo)](#tile-index-tile2difo)
  - [Tile Flags](#tile-flags)
  - [Texture Splatting](#texture-splatting)
- [World Object Placement](#world-object-placement)
  - [Object Index (object.ifo)](#object-index-objectifo)
  - [Object String Index (objectstring.ifo)](#object-string-index-objectstringifo)
- [Terrain Shader Pipeline](#terrain-shader-pipeline)
  - [Atmospheric Scattering (Distant Terrain)](#atmospheric-scattering-distant-terrain)
  - [Standard Terrain (Near)](#standard-terrain-near)
  - [Fog System](#fog-system)
  - [Self-Shadowing](#self-shadowing)
- [Water Rendering](#water-rendering)
  - [Ocean Vertex Displacement](#ocean-vertex-displacement)
  - [Animated Water Fallback](#animated-water-fallback)
- [Sky Rendering](#sky-rendering)
- [Shader File Reference](#shader-file-reference)
- [File Reference](#file-reference)

## Overview

Silkroad Online's terrain is a **tile-based heightfield** rendered across a large world grid. The system combines:

```
World Grid (~227 x 81 regions)
  ├── Per-region navigation mesh (.nvm) ─── terrain geometry + pathfinding
  ├── Tile textures (.ddj) ─── indexed by tile2d.ifo (603 textures)
  ├── World objects (.bsr) ─── indexed by object.ifo (2,767 objects)
  ├── Region info ─── town/field boundaries for shader selection
  └── Shader pipeline
        ├── Atmospheric scattering ─── distant terrain with Rayleigh/Mie
        ├── Texture splatting ─── 2-layer terrain blending
        ├── Normal/horizon maps ─── per-pixel lighting + self-shadow
        ├── Cloud shadows ─── projected from world XZ
        └── Dual fog ─── distance + height-based
```

## World Grid System

### Region Coordinates

The game world is divided into rectangular region tiles on a 2D grid. Each region covers a fixed area (1920 x 1920 world units based on observed coordinate ranges).

Region coordinates use two systems:

| System | Format | Example | Used By |
|--------|--------|---------|---------|
| Hex | `nv_XXYY.nvm` | `nv_198c.nvm` = (0x19, 0x8C) = (25, 140) | NVM files, objectstring.ifo |
| Decimal | `XXXxYYY` | `100x100` | Minimap tiles, regioninfo.txt |

Both systems reference the same grid. Convert between them: minimap decimal `100x100` = NVM hex `nv_6464.nvm`.

**World grid extent** (from minimap files): X: 26–252, Y: 37–117 (decimal), covering approximately 227 x 81 regions = 5,040 NVM files.

### Region Info

`shader/regioninfo.txt` (EUC-KR encoded) defines rectangular zones that control shader selection:

```
#TOWN   장안                         ← Town name (Korean)
167   99   RECT   0   220   1920   220   ← Region (167,99), partial coverage
168   98   ALL                           ← Region (168,98), full coverage

#FIELD  장안필드                      ← Field name
169   97   RECT   1720   0   1720   1920
165   94   ALL
```

- `#TOWN` regions use standard fixed-function lighting (no atmospheric scattering)
- `#FIELD` regions use the full atmospheric scattering pipeline
- `ALL` means the entire region tile; `RECT x1 y1 x2 y2` defines sub-region boundaries in local coordinates (0–1920 range)

### Map Info (MFO)

`navmesh/mapinfo.mfo` (JMXVMFO 1000, 8,216 bytes) stores a bitmap of active regions. After the 12-byte JMXV header, the remaining 8,204 bytes form a sparse lookup table indicating which world regions are populated with terrain data on this server build.

## Terrain Geometry

### Navigation Mesh (NVM)

Each region tile has a corresponding NVM file (`navmesh/nv_XXYY.nvm`) containing both the navigation mesh for pathfinding and the terrain geometry data. There are **5,040** NVM files ranging from ~74 KB to ~232 KB.

### NVM File Structure

```
Offset  Size    Description
0x00    12      JMXV header: "JMXVNVM 1000"
0x0C    2       Padding (0x0000)
0x0E    2       u16: vertex/cell count 1
0x10    2       Padding (0x0000)
0x12    2       u16: triangle/cell count 2
0x14    var     Mesh data: vertex positions (float x, y, z), triangle indices,
                cell adjacency, walkability flags
var     fixed   Cell grid lookup table (fixed-size grid for spatial queries)
```

**Observed count values:**

| File | Size | Count1 | Count2 | Description |
|------|------|--------|--------|-------------|
| Minimal (1,1) | ~74 KB | 1 | 1 | Empty/ocean region (mostly zeros) |
| Sparse (4,4) | ~75 KB | 4 | 4 | Simple terrain (e.g. flat desert) |
| Moderate (17,5) | ~75 KB | 17 | 5 | Slightly varied terrain |
| Dense (1801,907) | ~232 KB | 1801 | 907 | Complex terrain with many triangles |

The mesh data contains IEEE 754 single-precision floats encoding vertex positions in world space. Coordinate values observed in dense NVM files range from ~200 to ~1920, consistent with region-local coordinates.

Every NVM file includes a **fixed-size cell grid** (occupying the majority of the file in sparse regions) used for fast spatial lookups during pathfinding. Each grid cell is ~384 bytes with data followed by zero padding.

### Terrain Grid Construction

The terrain is rendered as a heightfield grid with vertices carrying:
- Position (x, y, z) — height encoded in the Y component
- Normal vector — for per-vertex or per-pixel lighting
- Up to 4 texture coordinates in `v4.xyzw` — for base texture and splatting detail

Heights are pre-computed in vertex buffers on the CPU; there is no GPU-side heightmap sampling.

## Terrain Texturing

### Tile Index (tile2d.ifo)

`navmesh/tile2d.ifo` (JMXV2DTI 1001) defines **603 terrain tile textures** used across all regions:

```
JMXV2DTI1001               ← Header (12-byte magic)
603                         ← Entry count
INDEX FLAGS "REGION" "FILENAME" {optional_params}

00000 0x00000000 "CJfild" "c_dust_fld_01.ddj"
00002 0x0000000a "CJfild" "c_grass_fld_03.ddj"
00007 0x0000000a "HMfild" "c_grass_hmfld_01.ddj" {757,64}
```

| Field | Description |
|-------|-------------|
| INDEX | Sequential tile ID (00000–00602) |
| FLAGS | Hex bitmask controlling surface behavior |
| REGION | Geographic zone name |
| FILENAME | DDJ texture file (in Data.pk2) |
| {x,y} | Optional world coordinate reference |

### Tile Flags

The flags bitmask controls surface rendering effects:

| Flag | Surface Type | Example Textures |
|------|-------------|------------------|
| `0x00000000` | Standard (dust, stone) | `c_dust_fld_*.ddj`, `bagh_city_tile*.ddj` |
| `0x00000001` | Earth | `c_dust_hmfld_*.ddj` |
| `0x00000003` | Marble/stone | `cj_marble_*.ddj` |
| `0x00000006` | Swamp | `c_dust_swmp_*.ddj` |
| `0x00000007` | Water/wet | `oaho_water_*.ddj` |
| `0x00000009` | Snow | `oakk_snow_sn_*.ddj` |
| `0x0000000a` | Grass (with grass effect) | `c_grass_fld_*.ddj` |

**Region name conventions:**

| Region | Area |
|--------|------|
| `CJfild` | Jangan (Chinese capital) field |
| `HMfild` | Hotan mountain field |
| `WC` | Western China |
| `OAKK` | Korean/Taklamakan area |
| `StormDesert` | Storm Desert |
| `Pharaoh` | Egyptian region |
| `Swmp` | Swamp |
| `Arabia` | Baghdad/Arabian region |

### Texture Splatting

Terrain uses a **2-layer texture splatting** system for blending tile textures:

```asm
; From vertexshader0splatting.c
mov oT0.xy, v4.xy              ; Base texture UV from vertex data
mul oT1.xy, v4.zw, c[VSC_TEXTUREANI_MATRIX].x  ; Detail UV (scaled)
```

- `v4.xy` provides the base/alpha map UV coordinates
- `v4.zw` provides the detail layer UV coordinates, scaled by a configurable factor
- The alpha channel of the base texture controls blending with the detail layer
- Per-vertex directional lighting is computed as `N.L` (normal dot light direction)

## World Object Placement

### Object Index (object.ifo)

`navmesh/object.ifo` (JMXVOBJI 1000) indexes **2,767 world objects** (buildings, nature, props):

```
JMXVOBJI1000
2767
INDEX FLAGS "BSR_PATH"

00000 0x00000001 "res\bldg\china\cj_ferry\cj_ferry_buil.bsr"
00012 0x00000000 "res\nature\china\dunhuang\ferry\w_cd_budawal.bsr"
```

Each entry maps a numeric object ID to a BSR resource path. The flags field (`0x00000000` or `0x00000001`) likely controls object properties such as collision.

### Object String Index (objectstring.ifo)

`navmesh/objectstring.ifo` (JMXVOBJI 1000) contains **189 named placement entries** with world coordinates:

```
REGION_HEX FLAGS REGION_X REGION_Y FLOAT_X FLOAT_Y FLOAT_Z FLOAT_ROT "NAME"

0x7de41001 0x00000000 228 125 0x44c4f380 0x44452cb2 0x4282d487 0x3fcad559
    "POS_STRUCTURE_GOD_BIG_GATE_TOGUI_1"
```

The float values are IEEE 754 hex-encoded world-space coordinates. Region coordinates (228, 125) identify the region tile, and the hex ID encodes both region and sub-region information.

## Terrain Shader Pipeline

The terrain rendering uses two shader paths based on distance and region type, with DirectX 8/9 assembly shaders (vs.1.1, ps.1.1, ps.1.4).

### Atmospheric Scattering (Distant Terrain)

Based on the work of **Nathaniel Hoffman, Kenneth J. Mitchell, and Arcot J. Preetham (2002)**, the scattering pipeline computes physically-based atmospheric effects:

**Vertex shader** (`scattervs10.vsh`):
1. Transform position to clip space and world space
2. Compute view direction: `V = eye - world_position`
3. Compute scattering angle: `cos(theta) = V . L` (view dot sun direction)
4. Compute Rayleigh phase: `Phase1 = 1 + cos^2(theta)`
5. Compute Mie phase (Henyey-Greenstein): `Phase2 = (1-g^2) / (1+g-2g*cos(theta))^1.5`
6. Compute extinction: `E = e^(-(Beta1 + Beta2) * distance)` scaled by terrain reflectance
7. Compute inscattering: `I = (Beta'1*Phase1 + Beta'2*Phase2) * (1-E) / (Beta1+Beta2)`
8. Project cloud texture from world XZ coordinates
9. Output: `oD0 = extinction`, `oD1 = inscattering`

**Pixel shader** (`terrainpsn10.psh` / `terrainps14.psh`):

```
; Rendering equation:
Surf_color = (N.L) * terrain_tex * cloud_covering * self_shadow_term
Final_color = Surf_color * extinction + inscattering
```

**Texture slots:**

| Slot | Content | Purpose |
|------|---------|---------|
| t0 | Normal/horizon map | RGB = packed normal, A = horizon angle for self-shadowing |
| t1 | Terrain color texture | Ground appearance (from tile2d.ifo) |
| t2 | Cloud layer | Projected from world XZ for cloud shadows |
| t3 | Detail texture | Additional detail layer (only in "detail" variants) |

### Standard Terrain (Near)

Near-terrain and town regions use a simpler fixed-function/vs.1.1 pipeline with multiple rendering modes selected by bitmask:

| Mode | Bitmask | Description |
|------|---------|-------------|
| Default | `0x00` | Single texture, directional light |
| Pre-baked | `0x02` | Diffuse vertex color (lightmap-like) |
| **Splatting** | `0x04` | **2-layer texture splatting** (primary terrain mode) |
| UV1 | `0x08` | Single UV, no lighting |
| UV2 | `0x10` | Splatting + ambient-only |
| UV3 | `0x20` | 3 texture layers |

Each mode has fog variants: `+0x40` for exponential fog, `+0x80` for height fog.

### Fog System

All terrain shaders implement a dual fog system:

**Distance fog** (exponential squared):
```
fog_dist = 1 / e^((z * density)^2)
```

**Height fog** (based on world-space Y):
```
height_delta = abs(world_y - fog_center_y)
fog_height = 1.0 - fog_intensity * max(0, height_delta - fog_range)
```

The two values are combined with `min` — the stronger fog wins:
```
final_fog = clamp(min(fog_dist, fog_height), 0.0, 1.0)
```

### Self-Shadowing

The terrain normal map's alpha channel stores a **horizon angle** — the elevation angle of the local terrain horizon at each texel. The pixel shader compares the sun's elevation against this stored angle:

```asm
sub_sat r0.a, c[CP_SUN_DIRECTION].a, t1.a   ; sun_elev - horizon_angle
mul r0, r0, 1-r0.a                           ; darken if sun below horizon
```

If the sun elevation is below the stored horizon angle, the pixel is in self-shadow. This provides cheap terrain self-shadowing without shadow maps.

Two shader variants exist for different normal map encodings: the `n` variants read the horizon angle from the alpha channel (`.a`), while the `p` variants read it from the blue channel (`.b`).

## Water Rendering

### Ocean Vertex Displacement

`oceanwater.vsh` implements **4-wave sinusoidal vertex displacement** using a Taylor series approximation of sin/cos:

**Wave parameters** (per-wave, 4 waves total):

| Constant | Description | Example Values |
|----------|-------------|----------------|
| c11 | Wave heights | (80.0, 100.0, 5.0, 5.0) |
| c12 | Wave offsets | (0.0, 0.2, 0.0, 0.0) |
| c13 | Wave speeds | (0.2, 0.15, 0.4, 0.4) |
| c14 | Wave direction X | (0.25, 0.0, -0.7, -0.8) |
| c15 | Wave direction Y | (0.0, 0.15, -0.7, 0.1) |
| c16 | Time | (time, sin(time)) |
| c17 | Base texcoord distortion | (0.031, 0.04, -0.03, 0.02) |

**Pipeline:**
1. Compute wave phase from texture coordinates and time: `phase = dir * uv + speed * time + offset`
2. Approximate sin/cos using Taylor series (up to 8th order)
3. Displace vertex position along normal by summed wave heights: `pos += normal * dot(sin_waves, wave_heights)`
4. Compute warped normals, tangents, and binormals for bump mapping
5. Transform to world space and pass view vector for Fresnel computation

**Pixel shader** (`oceanwater.psh`, ps.1.4): The active code outputs the bump map sample directly. The commented-out full pipeline includes:
- Cubic environment map reflection
- Fresnel term: `reflection * (1 - V.N)`
- Specular highlights raised to 8th power
- Water color blending

### Animated Water Fallback

`water/water101.ddj` through `water130.ddj` — 30 pre-rendered frames of animated water:
- Format: JMXVDDJ 1000 wrapping a 64x64 uncompressed RGBA DDS texture
- Size: ~16 KB each
- Used as a fallback for hardware that cannot run the vertex-displaced ocean shader

## Sky Rendering

The sky is rendered entirely through the atmospheric scattering system. The sky pixel shader (`skyps10.psh`) simply outputs the inscattering color from the vertex shader:

```asm
ps.1.1
tex t0          ; sample sky texture
mul r0, v0, t0  ; modulate by extinction
add r0, r0, v1  ; add inscattering
```

The sky dome geometry passes through the same scattering vertex shader as the terrain, but with the view direction pointing upward, producing the sky color gradient from Rayleigh and Mie scattering calculations.

## Shader File Reference

| File | Type | Description |
|------|------|-------------|
| `scattervs10.vsh` | VS 1.1 | Atmospheric scattering vertex shader |
| `scattervsdetail10.vsh` | VS 1.1 | Scattering with detail texture (4th UV) |
| `terrainpsn10.psh` | PS 1.1 | Terrain pixel shader (normal in RGBA) |
| `terrainpsp10.psh` | PS 1.1 | Terrain pixel shader (normal in RGBB) |
| `terrainpsndetail10.psh` | PS 1.1 | Terrain + detail texture |
| `terrainpspdetail10.psh` | PS 1.1 | Terrain + detail (alt normal) |
| `terrainps14.psh` | PS 1.4 | Terrain pixel shader (higher hardware) |
| `skyps10.psh` | PS 1.1 | Sky pixel shader |
| `oceanwater.vsh` | VS 1.1 | Ocean vertex displacement (4-wave) |
| `oceanwater.psh` | PS 1.4 | Ocean pixel shader (bump + env map) |
| `bumpwaves.vsh` | VS 1.1 | Simple water with projected bump coords |
| `vertexshader0splatting.c` | VS 1.1 | Near-terrain texture splatting |
| `vertexshader0.c` | VS 1.1 | Standard object vertex shader |
| `regioninfo.txt` | Config | Town/field region boundaries |

## File Reference

| File | Format | Location | Description |
|------|--------|----------|-------------|
| `nv_XXYY.nvm` | JMXVNVM 1000 | Data: `navmesh/` | Navigation mesh + terrain geometry (5,040 files) |
| `tile2d.ifo` | JMXV2DTI 1001 | Data: `navmesh/` | Terrain tile texture index (603 entries) |
| `object.ifo` | JMXVOBJI 1000 | Data: `navmesh/` | World object BSR index (2,767 entries) |
| `objectstring.ifo` | JMXVOBJI 1000 | Data: `navmesh/` | Named world positions (189 entries) |
| `mapinfo.mfo` | JMXVMFO 1000 | Data: `navmesh/` | Active region bitmap |
| `regioninfo.txt` | Text (EUC-KR) | Data: `shader/` | Town/field zone definitions |
| `water*.ddj` | JMXVDDJ 1000 | Data: `water/` | Animated water frames (30 files, 64x64) |
| `ainavdata_*.dat` | Binary | Data: `navmesh/` | AI navigation/spawn data (18 files) |
| `XXXxYYY.ddj` | JMXVDDJ 1000 | Media: `minimap/` | Region minimap tiles (4,483 files) |
| `*.dof` | JMXVDOF 0101 | Data: `dungeon/` | Dungeon layouts (21 files) |
| `dungeoninfo.txt` | Text (EUC-KR) | Data: `dungeon/` | Dungeon ID → DOF path index |

## See Also

- [Asset File Formats](asset_formats.md) - Complete reference for all file formats inside PK2 archives
- [Character & Equipment Rendering](character_rendering.md) - How characters are assembled and rendered
- [PK2 Format](pk2_format.md) - PK2 archive structure and encryption
- [Network Protocol](network_protocol.md) - Network packet format, handshake, and encryption

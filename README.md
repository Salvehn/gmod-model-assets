# Garry's Mod model assets

Shared model and texture storage for Salvehn's Starfall builds.

## Quadra Type-66 Avenger / noralee

Assets: [`quadra_type66_avenger/noralee`](quadra_type66_avenger/noralee).

This experimental build uses the primary visible geometry of the existing
Prop2Mesh dupe. It does not load the full original source model. P2M's auxiliary
normal-control triangles are replaced by explicit OBJ normals. Coplanar shader
normal transport overlays are represented with the baked normal texture;
physical details and traced radiator/intake openings are retained.

Color and surface detail come from one shared color atlas and one DirectX
normal atlas. There are no P2M palette/material/color partitions in the Starfall
visual. Glass uses the same atlas with a separate translucent shader. Functional
lamp sections retain independent light states.

Meshes are combined by independently moving node. Source's limit of 65,535
expanded vertices requires internal GPU chunks for large nodes. Downloads are
batched by node and use GMod-compatible known-size LZMA. Identical wheel meshes
are downloaded and allocated once, then instanced on the other side.

`manifest.json` records moving slots, chunk bounds, transport batches and sizes.
Loaders should pin an asset commit instead of following a mutable branch.

Requires StarfallEx, Wiremod, AdvDupe2, and the existing raycast vehicle setup.
The local Starfall native dupe embeds only its visual loader; the common E2
controller and matching Starfall preset are loaded separately from disk.

Offline parser/compiler checks are not an in-game performance or appearance
certification. Source's Phong, reflections and transparency approximate the
source game's shaders. The texture atlas prioritizes batching and download size.

Original vehicle design and game-derived assets belong to their respective
rights holders. This repository does not claim ownership of those assets.

## Segway SuperScooter GT3 / Starfall

Assets: [`segway_superscooter_gt3/gt3_sf`](segway_superscooter_gt3/gt3_sf).
This folder contains the mesh packets, texture atlases and checksum manifest
used by the GT3 Starfall dupe. The loader pins the asset commit.


## MV Agusta Brutale 1000 Serie Oro / Starfall

Assets: [`mv_agusta_brutale/brutale_sf`](mv_agusta_brutale/brutale_sf).
This folder contains the compressed mesh packets, textures and checksum
manifest for the Starfall dupe. The loader pins the asset commit.
The input mesh credits VTX.

Download [the AdvDupe2 paste](mv_agusta_brutale/mv_agusta_brutale_starfall.txt)
to `garrysmod/data/advdupe2/`, then paste with parenting enabled.
Requires StarfallEx, Wiremod / AdvDupe2, and SProps.
The paste downloads its assets from the pinned mirror at runtime.

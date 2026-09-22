# VPW Example Tables (extracted)

Extracted copies of the [VPin Workshop Example Resource Tables](https://vpuniverse.com/files/file/7787-vpin-workshop-example-resource-table/), used as sample assets by [vpx-editor](https://jsm174.github.io/vpx-editor/) ([source](https://github.com/jsm174/vpx-editor)).

## Credits

All tables are the work of the [VPin Workshop (VPW)](https://vpuniverse.com/files/file/7787-vpin-workshop-example-resource-table/) team. I take no credit for them. This repository only holds them in an extracted form so they can be loaded as assets.

## Contents

| Folder | Table | Version |
| --- | --- | --- |
| `Basic Example Table VPW 1.7.1/` | Basic VPW Example Table | 1.7.1 |
| `Example Table VPW 1.7/` | VPW Example Table | 1.7 |
| `ROM Example Table VPW 1.7/` | ROM Example Table VPW | 1.7 |
| `VPWExampleTableDMD/` | DMD assets (fonts, images, animations) used by the example tables | |

Each table folder contains the output of a `vpxtool extract` run:

- `script.vbs` – the table script
- `gamedata.json`, `info.json`, `version.txt` – table properties and metadata
- `gameitems.json` and `gameitems/` – one JSON file per game item (bumpers, flippers, walls, primitives, etc.)
- `images.json` and `images/` – playfield and texture images
- `sounds.json` and `sounds/` – sound files
- `fonts.json` and `fonts/` – embedded fonts
- `materials.json`, `collections.json`, `renderprobes.json` – materials, collections and render probes

## How they were extracted

The tables were extracted with [vpxtool](https://github.com/francisdb/vpxtool) 0.34.6:

```sh
vpxtool extract "Example Table VPW 1.7.vpx"
```

The original `.vpx` files can be rebuilt from the extracted folders with:

```sh
vpxtool assemble "Example Table VPW 1.7"
```

## Refreshing after a vpxtool release

The JSON layout follows the [vpin](https://github.com/francisdb/vpin) library that vpxtool bundles, so a new release can change how records are written (field names, optional records, enum encodings). To move the folders to a new version without touching the tables themselves, rebuild each `.vpx` with the version that produced the current folders, then extract it again with the new version:

```sh
# with the previous vpxtool (0.33.10)
vpxtool assemble -f "Example Table VPW 1.7" "/tmp/Example Table VPW 1.7.vpx"

# with the new vpxtool (0.34.6)
rm -rf "Example Table VPW 1.7"
vpxtool extract -f -o "Example Table VPW 1.7" "/tmp/Example Table VPW 1.7.vpx"
```

The resulting commit contains only the format differences between the two versions.

| Extracted with | Assembled from |
| --- | --- |
| vpxtool 0.33.10 | the VPW downloads |
| vpxtool 0.34.6 (vpin 0.37.0) | the 0.33.10 folders, assembled with vpxtool 0.33.10 |

## License

The tables remain the property of their original authors at VPW. See the [download page](https://vpuniverse.com/files/file/7787-vpin-workshop-example-resource-table/) for their terms.

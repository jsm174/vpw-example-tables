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

The tables were extracted with [vpxtool](https://github.com/francisdb/vpxtool) 0.33.10:

```sh
vpxtool extract "Example Table VPW 1.7.vpx"
```

The original `.vpx` files can be rebuilt from the extracted folders with:

```sh
vpxtool assemble "Example Table VPW 1.7"
```

## License

The tables remain the property of their original authors at VPW. See the [download page](https://vpuniverse.com/files/file/7787-vpin-workshop-example-resource-table/) for their terms.

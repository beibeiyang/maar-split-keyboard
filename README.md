# Maar Split Keyboard

A split ergonomic keyboard based on [christianselig/caldera-keyboard](https://github.com/christianselig/caldera-keyboard), adapted for **Kailh Choc V2 (PG1353) low-profile** switches. I personally use the [Kailh Purple Iris Silent Mini Low Profile Switch](https://ymdkey.com/products/kailh-purple-iris-silent-mini-low-profile-switches-linear-fast-actuation-3-pin-for-hitbox-low-profile-keyboards) (linear, silent, 30 gf, 0.8 mm actuation, 1.8 mm total travel).

## Differences from the original Caldera

| | Original Caldera | This project |
|---|---|---|
| Switch | Kailh Choc V1 (PG1350) low-profile | Kailh Choc V2 (PG1353) low-profile |
| Switch footprint | ergogen built-in `choc` | ceoloide `switch_choc_v1_v2` (V2-only) |
| Hotswap | Yes | Yes |

Key footprint changes:
- `choc_v1_support: false` — removes V1 lateral stabilizer/boss holes
- `choc_v2_support: true` — uses the 5 mm center hole required by V2 switches
- Choc V2 switches use an MX-compatible stem; keycap compatibility differs from V1

## Generating the PCB

Requires [Ergogen](https://ergogen.cache.works/) v4:

```bash
npm install -g ergogen
```

The `footprints/` directory is shared via a symlink. After cloning, create it if it doesn't exist:

```bash
ln -s ../footprints ergogen/nice_nano/footprints
```

Run ergogen from the variant subdirectory so it picks up the config and footprints:

```bash
cd ergogen/nice_nano && ergogen .
```

Output files land in the respective `output/` subdirectory:
- `output/pcbs/left.kicad_pcb` and `output/pcbs/right.kicad_pcb` — open in KiCad
- `output/outlines/` — DXF outlines for case/plate cutting
- `output/cases/plate.jscad` — plate model

## Credits

- **[christianselig/caldera-keyboard](https://github.com/christianselig/caldera-keyboard)** — original Caldera keyboard design, layout, PCB config, and custom footprints (`EVQPUC.js`, `mountinghole.js`, `nice_nano.js`, `text.js`). Licensed under the terms of that project.
- **[ceoloide/ergogen-footprints](https://github.com/ceoloide/ergogen-footprints)** — `switch_choc_v1_v2.js` footprint. Licensed under [CC-BY-NC-SA-4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
- **[Ergogen](https://github.com/ergogen/ergogen)** — keyboard layout generator framework.

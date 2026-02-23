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

Run ergogen on the **directory** (not the yaml file directly) so it picks up the custom footprints:

```bash
cd ergogen
ergogen .
```

Output files land in `ergogen/output/`:
- `ergogen/output/pcbs/left.kicad_pcb` and `ergogen/output/pcbs/right.kicad_pcb` — open in KiCad
- `ergogen/output/outlines/` — DXF outlines for case/plate cutting
- `ergogen/output/cases/plate.jscad` — plate model

## Credits

- **[christianselig/caldera-keyboard](https://github.com/christianselig/caldera-keyboard)** — original Caldera keyboard design, layout, PCB config, and custom footprints (`EVQPUC.js`, `mountinghole.js`, `nice_nano.js`, `text.js`). Licensed under the terms of that project.
- **[ceoloide/ergogen-footprints](https://github.com/ceoloide/ergogen-footprints)** — `switch_choc_v1_v2.js` footprint supporting Kailh Choc V1 and V2 switches. Licensed under [CC-BY-NC-SA-4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
- **[Ergogen](https://github.com/ergogen/ergogen)** — keyboard layout generator framework.

# MLCC_Stacking_Practical_Guide

Open-source stencil PCB design files for "Multilayer MLCC Stacking: A Practical
Guide to Increasing Power Density for High-Performance Computing Applications"
(IEEE APEC 2027).

The stencil enables reproducible prototyping of vertically stacked Class II
multilayer ceramic capacitor (MLCC) assemblies from off-the-shelf parts with
standard reflow soldering. The stacks are prefabricated in the stencil and then
mounted on the target PCB as single components during regular SMD assembly.

## Contents

| File | Description |
|---|---|
| `20251010_MLCC_Stacking_PCB_Stencil_v2.PcbDoc` | Altium Designer layout of the stencil PCB |
| `20251010_MLCC_Stacking_PCB_Stencil_v2.pdf` | Drawing of the stencil PCB with the cavity arrays |
| `Gerber_MLCC_Stacking_PCB_Stencil_v2.zip` | Manufacturing data (profile with board cutouts, legend, mechanical layer) for ordering the stencil from any PCB service |
| `LICENSE` | CERN-OHL-P-2.0 license text |

## Stencil design

- Standard 1.6 mm FR-4 PCB with non-plated cavities milled as board cutouts
  with rounded ends
- Each cavity holds a rectangular array of capacitors:
  - 0402: 1x2, 1x6, 1x15, 1x20, 2x6, 2x20, 3x20, 4x20, 10x2, 10x4
  - 0603: 1x10, 2x10, 3x10, 4x10, 10x1, 10x2, 10x3, 10x4
  - 0805: 1x2, 1x5, 3x1, 1x10, 2x10, 3x10, 4x10, 10x1, 10x2, 10x3, 10x4
- Cavity clearance: 0.2 mm in both directions for 0603 arrays, about
  0.17 mm to 0.18 mm per capacitor for most 0402 and 0805 arrays
- Several stencil boards can be stacked on top of each other, so the stencil
  does not limit the stack height.

## Stacking process

1. Place the first capacitor layer upside down on Kapton tape inside the
   stencil cavity.
2. Apply solder paste (type 5) to the exposed terminations with a thin
   dispensing needle, a precision pneumatic fluid dispenser, or a fine tip
   that transfers the paste.
3. Place the next capacitor layer or a pre-assembled sub-block.
4. Reflow. Vapor-phase reflow with Galden LS230 gave consistent results;
   surface tension self-aligns the layers.
5. Repeat steps 2 to 4 until the target stack height is reached.
6. Mount the finished stack on the target PCB like a single component.

Reflow profile: standard profile of the utilized solder paste.

Rework: stacks that leave the stencil slightly skewed are reflowed once more
outside the stencil. Surface tension and the cuboid shape of the MLCCs pull
the stack back into a block with orthogonal edges.

## Citation

If you use these files, please cite:

```bibtex
@inproceedings{winkler2027mlccstacking,
  author    = {Winkler, Joseph and Niemeyer, Jonas and Wicht, Bernhard},
  title     = {Multilayer {MLCC} Stacking: A Practical Guide to Increasing Power Density for High-Performance Computing Applications},
  booktitle = {Proc. IEEE Appl. Power Electron. Conf. Expo. (APEC)},
  year      = {2027},
  note      = {to appear}
}
```

## Authors

Joseph Winkler, Jonas Niemeyer, Bernhard Wicht
Institute of Microelectronic Systems, Leibniz University Hannover, Germany

## License

The design files are released under the CERN Open Hardware Licence Version 2,
Permissive (CERN-OHL-P-2.0). See `LICENSE`.

SPDX-License-Identifier: CERN-OHL-P-2.0

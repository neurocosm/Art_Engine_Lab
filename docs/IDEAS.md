# Ideas and Feature Inventory

This is an **exploration inventory**, not a committed feature specification.

## Raster reconstruction

- Import PNG and other common raster formats.
- Analyze palette, shapes, contours, gradients, text regions, symmetry, lines, and repeated motifs.
- Compare approaches: automatic path tracing, geometry recognition, manual redraw, and AI-suggested structured layers.
- Keep a visible original-vs-reconstruction comparison.
- Offer modes such as faithful reconstruction, cleaned-up, stylized, and tile extraction.

## Tiling and pattern design

- Define exact tile width, height, and repeat basis.
- Support straight grid, half-drop, brick/stagger, and (eventually) mirrored and rotational patterns.
- Provide **X/Y controls**, perhaps with both sliders and numerical input.
- Keep **tile-origin/phase adjustment**, **repeat lattice/stagger adjustment**, and **motif-in-tile position** conceptually separate. These are different transformations.
- Include live 1×1 and 3×3/5×5 repeat previews; optional full-screen/fabric previews.
- Offer a seam-debug view with highlighted edges/corners and before/after comparison.
- Check horizontal and vertical edge periodicity for raster outputs and continuity where possible for vector shapes/strokes.
- Allow creative offsets, including deliberate seams or misregistration, with clearly differentiated "seamless" and "intentional offset" modes.
- Examine visual rhythm, obvious repetition, motif density, and negative space without confusing subjective scoring with a mathematical guarantee.


### Pattern rotation, shear, and lattice arrangements (proposed)

- Add an **Angle / Rotation** control (slider or rotary knob, degrees) that rotates the whole repeating pattern, not merely an individual brick; keep a reset-to-zero action.
- Add a separate **Slant / Shear** control to skew the repeat basis. Do not confuse shear with rotation or with brick-to-brick stagger.
- Explore arrangement presets such as **rotated running bond**, **straight grid**, **herringbone**, **basketweave**, and **diamond/oblique lattice**. These may require *different algorithms*, not just a visual transform.
- Consider independent **brick orientation** as a further control, distinct from rotation of the whole lattice.
- Display repeat-basis vectors / transformed tile boundaries as a diagnostic overlay, and provide an unclipped larger repeat preview so artistic effects are understandable.
- The transformed positions can be expressed with lattice vectors `p(i,j) = p0 + i·u + j·v`. Rotation or shear changes `u` and `v`; arrange geometry coherently across neighboring copies.
- **Crucial export distinction:** An arbitrarily rotated/sheared lattice may repeat perfectly on a *parallelogram* cell or inside SVG using transformed pattern coordinates, but need not have a small axis-aligned rectangular PNG/SVG tile that repeats seamlessly by simple horizontal/vertical translation. Do not promise that automatically. Test actual exported repeat bounds and corners; where necessary use transformed SVG patterns, derived repeat periods, a valid larger repeat cell, or mark rectangular seamless export as unavailable for a chosen transformation.
- Artistic offsets/misregistration may deliberately break seams; clearly distinguish them from correctly periodic transformations.
- **Status:** Idea for a later Experiment 002 iteration / broader Tile Lab research. Basic geometry and three reference palettes remain the first implementation priority.

### Surface FX / Realism (proposed)

Aim to recreate the **material character** of the original brick reference art while preserving mathematically well-defined base geometry.

- Use separately controllable **brick-only**, **grout-only**, **both**, and optional **global overlay** effect targets. Distorting bricks must not accidentally distort grout if the artist selected bricks only.
- Consider controls for organic edge/shape distortion, micro-chips and nicks, cracking, pores/pitting, scratches, chipped corners, weathering, stains, grime, color drift, uneven highlights/shadows, relief/depth, and texture intensity.
- Keep effects **reversible and non-destructive**: geometry, materials/texture, and oddities should be separately toggleable. A clean vector mode remains available.
- Use deterministic **FX seeds** and seeded per-brick variation so the exact same tile can be regenerated and exported consistently. Consider a "randomize FX seed" button with locks for protected settings.
- Surface distortion or chips need to be applied in a way that preserves shared material edges and expected grout appearance. Seam-crossing effects should wrap with the lattice so exports stay periodic.
- Explore SVG paths/filters for scalable or procedural effects; Canvas/WebGL can be used for more complex rendering, but raster filters/pixels are **not inherently vector paths**. Do not label a mixed result fully vector.
- Add a **realism intensity** control that ranges from clean graphic shapes through restrained physical texture to heavily weathered surfaces. Compare reference and output at multiple zoom levels and print sizes.

### Oddity / Easter Egg layer (proposed)

Create optional hidden narrative details without forcing them into every design.

- Include rare anomalous bricks or playful silhouettes (e.g. **lizard-shaped brick**), replacements, hidden pictograms, little carved marks, initials, and inside jokes.
- Support optional editable graffiti/spray-paint layers, with user-entered text such as **"Kilroy was here"** or **"NO NUKES"**, small doodles, and stenciled marks.
- Consider **Off / Subtle / Playful / Wild** modes, oddity frequency / rarity, graffiti density, text choice, random surprise, lock controls, and a separate oddity seed.
- **Seam-safe** mode must correctly wrap oddities across boundaries; **freeform** mode may intentionally create visible seams or a one-off unique graphic. Clearly label the difference.
- A repeat cell will repeat its oddity too: if the goal is a *single* rare oddity across a larger printed area, use a larger supercell or an export-stage placement layer, rather than pretending a tiny tile can contain a globally unique event.
- Leave the artist in charge. AI may suggest context-sensitive geek humor and visual details, but must not silently insert or overwrite the artwork.

**Scope:** Future Tile Lab exploration, not initial Experiment 002 requirements. Preserve original imagery and get base geometry, palettes, repetition and export behavior sound first.

## Bandana Lab — Borderless Continuity (foundational decision)

- **Experiment 003's primary mode is a mathematically seamless, visually continuous, borderless ornament field** inspired by bandana paisley, florals, vines, rosettes and detail. Do **not** repeat framed square bandanas or expose an outer/inner frame.
- Flowing motif clusters must wrap across the cell's edges/corners. Test the actual exported repeat and independently inspect a 3×3/5×5 field for obvious grids, medallion repetitions and blank patches; mathematical wrapping does not guarantee attractive or invisible repeats.
- Preserve the existing framed prototype while developing the new default. Optional framed mode can remain as an explicit alternative.
- **Foundation spec:** [Bandana Lab — Borderless Seamless Ornament](BANDANA_LAB_FOUNDATION.md).

## Bandana Lab — Outsider Accent Blend (proposed)

- For future **Experiment 003 — Bandana Lab**, preserve the continuous traditional ornament vocabulary (paisley, floral/vine strands, rosettes, fillers) while subtly blending in recognizable nontraditional micro-motifs.
- Provide an opt-in **Traditional ↔ Outsider Accent Blend** control, distinct from the shared Historical Accuracy ↔ Creative License AI setting; the default should favor a classic look.
- Potential motif families: **zodiac constellation sprites** (tiny stars joined by fine, pale lines), **Saturn** and other planets/moons, a small **atom/energy emblem**, kaleidoscopic symmetry, fractal-inspired self-similar curls, and tiny nature surprises (such as a lizard).
- Make accents **discoverable rather than dominant**. Integrate their lines, scale and colors into the existing ornament, rather than pasting on stickers or displacing the primary motif vocabulary.
- Offer eventual artist controls for family, amount, **placement inside motif streams or filler gaps**, subtlety/recognizability, frequency, deterministic seed, and reset; keep them editable and removable, periodic in seamless mode.
- Use reusable SVG vector motifs with readable actual-print-size line weights. If a pattern is stylized rather than a faithful zodiac star configuration, label it as constellation-inspired.
- **Detailed spec:** [Bandana Lab Outsider Accents](BANDANA_LAB_OUTSIDER_ACCENTS.md).
- **Status:** Future exploratory concept, not part of the current Experiment 003 coding task; no changes to unfinished app files.

## Rendering techniques

- SVG: paths, geometry, gradients, patterns, outlined typography, scalable motifs.
- Canvas 2D: pixel-based operations, source comparison, raster preview, export.
- WebGL/shaders: optional glow, distortion, procedural effects, and accelerated compositing.
- Shared scene/layer description could eventually separate design intent from the renderer implementation.

## AI assistance (future)

- Interpret a reference raster and suggest candidate logical layers.
- Infer likely motifs and repeat cells, with user confirmation.
- Recommend reconstruction methods, generate geometry/code, and describe uncertainty.
- Accept creative prompts to build/edit an artwork composition.
- Keep users able to inspect and revise AI-proposed structures; avoid pretending AI has measured exact geometry if it has not.

## Output and production experiments

- Export genuinely vector designs as SVG.
- Export previews/finished images as PNG, possibly at specified dimensions and resolution.
- Explore print workflows for T-shirts, sweatshirts, and all-over patterns, with later checks for color profiles, bleed, repeat scale, and vendor-specific specifications.

## Candidate first demonstrations

1. Tile Lab: import a user-supplied tile, adjust X/Y phase and repeat modes, show repeated preview, export.
2. Rebuild a clean logo or simple banner as layered SVG and compare with source.
3. Generate procedural PCB-inspired ornamental paths as repeatable SVG motifs.

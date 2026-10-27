# Experiment 003 — Bandana Lab: Borderless Seamless Ornament (Foundational Direction)

**Status:** **Agreed foundational design decision** (2026-10-26), replacing the earlier assumption that Experiment 003's primary output is a framed square bandana.
**Scope:** Art Engine Lab / Tile Lab / Experiment 003 — Bandana Lab.
**Related:** [Outsider Accent Blend and recognizable micro-motifs](BANDANA_LAB_OUTSIDER_ACCENTS.md).

## The essential idea

> **Capture the spirit of bandana ornamentation as a continuous surface: the repeat unit should disappear into the artwork rather than visibly frame or silo it.**

The art is *bandana-inspired*, not a repeating mosaic of complete, bordered square bandanas. Preserve the visual vocabulary of paisley, curling vines, filigree, florals, dots, small medallions, rosettes and intricate fillers—but let the artwork flow naturally across a surface with **no outer or inner perimeter frame by default**.

A computer needs a repeat period; a person looking at the finished artwork should not see a rectangle-shaped tile.

## Foundational requirements

1. **No visible bandana frame in the primary mode.** Avoid perimeter borders, decorated edges, four-corner layouts, and a single large center medallion whose repetition exposes a grid. Do not simulate continuity merely by copying a framed bandana across and down.
2. **Genuine mathematical periodicity.** Geometry **and strokes/effects** crossing left/right or top/bottom repeat boundaries must continue seamlessly on the corresponding opposite boundary, including corners.
3. **Visual continuity, separately judged.** Even a perfectly wrapped tile can show detectable repeated motifs, regular voids, rows, columns, or medallion grids. Treat these as artistic issues, distinct from seam errors.
4. **Organic ornamental flow.** Compose paisley/vine/floral strands, curvilinear clusters and filler shapes using varying scales, angles and densities; allow coherent paths and visual rhythms to cross cell edges.
5. **Artist-controlled variety.** Preserve selectable style families (Traditional Paisley, Western, Botanical/Floral, Geometric/Art Deco, Psychedelic); reinterpret former `Border`, `Corner`, `Center` controls as **flow type, main motifs, clusters, fillers, density, scale, variation and distribution** where appropriate. Avoid presenting controls that suggest the result is a framed square.
6. **Outsider accents remain optional.** Tiny constellations/zodiac star-lines, Saturn, atom/energy symbols, kaleidoscopic/fractal-like flourishes and tiny nature surprises are integrated into ornamental strands or gaps—not positioned according to an outer frame. Small blend levels should be nearly invisible until inspected closely.
7. **Vector-first.** Prefer editable, self-contained SVG geometry for motifs and exported patterns. Clearly disclose raster or filter limitations if introduced later. Do not silently add external assets, services or APIs.
8. **Preserve the working Codex prototype** while iterating. This decision changes the target direction; it is not a command to delete or overwrite Experiment 003's existing implementation. Migrate incrementally and keep the old framed composition as a *separate optional mode/reference* only if useful, never the primary default.

## Two different meanings of 'seamless'

### A. Seam correctness — objective

For a rectangular repeat of width `W` and height `H`, the rendered periodic field `F` satisfies:

- `F(x + W, y) = F(x, y)`
- `F(x, y + H) = F(x, y)`

The implementation should correctly wrap path segments, strokes, filters where applicable, and micro-motifs across edges and corners. A 1×1 cell is a construction/debug tool, **not** the sole artistic preview.

### B. Concealed repetition — perceptual

The artwork should not shout "same square again" when tiled. Test visual rhythm in a larger **3×3 or 5×5** view and at realistic print/fabric scales. Look for repeated focal points, symmetrical grids, unusual blank patches, oversized motifs, and conspicuous recurring outsider icons.

A mathematically repeatable design can still look visibly tiled. No single numeric metric guarantees a non-obvious repeat; visual review by the artist remains essential.

## Composition and repeat architecture (proposals, not prescribed algorithms)

- Represent the period as a repeat cell with separately editable paths/motif instances that may overlap/cross any edge. Generate all necessary translated copies, or use equivalent valid SVG pattern/wrapping logic.
- Consider interlaced **ornament streams**: vines, connected paisleys, filigree, leaves and filler motifs, each with distinct scale and phase.
- Vary orientations, spacing, density and motif weighting within a coherent stylistic vocabulary. Use deterministic seeds for repeatability; control variation without introducing gaps at wrap boundaries.
- Consider **larger supercells**, multi-scale distribution or carefully balanced motifs when a small repeat makes its boundaries perceptually obvious. A larger cell does not by itself guarantee invisible repetition.
- Avoid centering all large motifs in identical positions per repeat, even if the math is seamless.
- If implementing rotation or shear, heed Tile Lab's general note: a valid oblique periodic lattice is not necessarily a seamless *axis-aligned rectangular exported bitmap*. Don't promise rectangular seamless export without testing the selected basis.
- A rare Easter egg inside a repeating cell repeats every period too. If truly rare placement over a much larger fabric is desired, use a suitable **larger repeat supercell**; a one-off nonperiodic placement layer must be explicitly labeled **nonseamless/freeform** rather than claimed repeat-safe.

## Preview, controls and export direction

**Artwork View (default)**
- Display an uninterrupted 3×3/5×5 or zoomable larger field with **no visible guides, outer border or cell outline**.
- Keep the artwork in view while adjusting controls, preserving the existing useful preview/control layout.

**Engineering View (toggle)**
- Show repeat-cell outlines, seam-crossing motifs, cell boundaries and/or origin/phase; make these guide overlays absent from exports.
- Offer 1×1 debug alongside the multi-repeat view; show joined edges and corners clearly.

**Proposed artist controls**
- Base motif/style family, paisley/vine/floral/rosette options and complementary small-fillers.
- Flow direction, motif size range, density, spacing, rotation/orientation variation, distribution/cluster balance.
- X/Y phase of the **periodic field**, where relevant, kept distinct from movement of individual motifs or edits to the repeat basis.
- Colorway, deterministic seed/randomize, preview scale, seamless diagnosis, export.
- Optional **Outsider Accent Blend** with type/rarity/placement/recognizability (see linked spec).

Export SVG of the actual periodic pattern or the requested repeat artwork. Clearly state whether export is a reusable repeating cell or a larger composed artwork. Verify the **exported artifact**, not just the editor preview; avoid exporting debug overlays.

## Proposed acceptance checks for the Codex redesign

- [ ] Default composition uses **no framed-bandana edges** and no forced four-corner/center medallion composition.
- [ ] Main motifs and connecting ornaments extend naturally across the repeat boundaries.
- [ ] 3×3/5×5 view has exact seam continuity left↔right, top↔bottom, including corners.
- [ ] No obvious checkerboard/grid of identical framed bandanas; inspect for detectable periodic focal points.
- [ ] Artwork View hides all cell boundaries; Engineering View exposes them when requested.
- [ ] Exported SVG is self-contained, vector where claimed, and repeats identically to the live preview.
- [ ] Adjusting palette, flow, motif distribution, density and seed preserves intended periodicity.
- [ ] Existing Codex functionality is migrated cautiously; test coverage and honest caveats are retained.
- [ ] Outsider accents remain rare and integrated at low settings; rare accents follow the same wrap logic when seamless export is enabled.

## What this changes and does not change

- **Changes:** Experiment 003's **primary design objective**. Classic square bandana framing is now a reference/optional secondary mode, not the default target. Controls and composition algorithms should be rethought around a borderless repeated field.
- **Does not change:** Other Tile Lab experiments, overall Art Engine Lab technology choices, the shared AI policy, or the documented Outsider Accent motif library.
- **Implementation status:** Documentation and direction only. The working Experiment 003 code is being developed separately in Codex and must be reviewed before repository integration.

**Design checkpoint:** The viewer should first see continuous, bandana-inspired ornamentation—not a collection of little bandanas. Only close inspection should reveal where one mathematical period ends and the next begins.

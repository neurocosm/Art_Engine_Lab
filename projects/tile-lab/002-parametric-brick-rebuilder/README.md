# Experiment 002 — Parametric Brick Tile Rebuilder

**Project:** Art Engine Lab / Tile Lab  
**Status:** Planned — Ready for Experimentation  
**Technology:** HTML, CSS, JavaScript, SVG  
**Development approach:** Learning through mathematical reconstruction

## Vision

Reconstruct a family of existing raster brick patterns as scalable, editable vector artwork.

Instead of tracing individual pixels, the application should recognize and reproduce the mathematical structure responsible for the original designs.

The experiment emphasizes the relationship between precision, repeating geometry, color, texture, and artistic control.

## Original References

Three reference designs are provided:

1. **Patriotic Brick Pattern:** Red, white, and blue variations.
2. **Camouflage Brick Pattern:** Olive, green, khaki, brown, and earthy tones.
3. **Autumn Brick Pattern:** Orange, red, gold, olive, and brown variations.

The three designs appear to share a common vertical staggered brick layout.

Original reference images must be preserved without modification.

## Geometry Engine

Use a mathematical system with adjustable parameters:

- Brick width and height
- Horizontal and vertical grout spacing
- Stagger percentage
- Corner radius
- Pattern repeat dimensions
- Global X/Y phase shift
- Deterministic placement and color assignments

The system must produce an actual periodic pattern. The exported tile should repeat without introducing new edge or corner discontinuities.

## Color and Appearance

Start with three named palette presets.

Allow individual palette colors and grout colors to be adjusted in future versions.

Use deterministic color assignment so exported tiles reproduce consistently.

## User Interface

Include:

- Single tile preview
- Repeated pattern preview
- Geometry adjustment sliders
- Palette selection
- X/Y phase controls
- Tile boundary overlay
- Reset function
- SVG export

The interface should remain simple enough to help the user understand how geometry changes affect the finished pattern.

## Development Phases

### Phase A — Geometry
Rebuild the staggered brick structure using SVG shapes. Prove seamless repetition.

### Phase B — Colors
Implement the three palette presets and editable color assignments.

### Phase C — Surface Appearance
Explore subtle shadows, grain, distress, pores, texture, and dimensional shading.

Preserve vector geometry wherever possible, and disclose any raster-based effects.

### Phase D — Reconstruction Comparison
Compare output to the reference rasters for geometry, color, proportions, and appearance.

### Phase E — Artistic Exploration
Experiment with alternative repeat structures, offsets, palettes, and surface effects.


## Proposed Extension — Angle Offset and Lattice Styles (not part of initial build)

Following the initial brick geometry and palette reconstruction, explore controls for transforming the **entire final pattern**:

- **Angle / Rotation:** Rotate the full repeating brick field around a defined origin, measured in degrees. Provide slider/knob, numeric readout, and reset.
- **Lattice Slant / Shear:** Skew the pattern's repeat geometry independently of rotation.
- **Arrangement modes:** Original vertical staggered running bond, rotated running bond, straight grid, herringbone, basketweave, and diamond/oblique lattice.
- **Brick orientation:** Potential separate control; turning bricks individually is *not* equivalent to rotating the entire field.
- **Live preview:** Show both the transformed pattern and any applicable repeat-cell boundaries / lattice vectors so the artist can judge how it looks.
- **Artist choice:** Allow aesthetically pleasing deliberate offsets while labeling when the result is *not* seamless.

### Repeat geometry and export caveat

Treat the repeat system as a lattice with points `p(i,j) = p0 + i·u + j·v`, where `u` and `v` are period vectors. A rotation or shear transforms these period vectors along with the shapes; mathematically periodic geometry can still be seamless in its **own transformed cell**.

However, **arbitrary angles do not necessarily yield a seamless, axis-aligned rectangular raster tile**. The rotated pattern may require a parallelogram repeat cell, SVG `patternTransform`, derived rectangular period vectors where they exist, or an explicit export limitation. Cropping a rotated preview to a rectangle is **not** automatically a seamless tile.

For any newly supported transform, test the actual repeat behavior across all exported boundaries and corners, not merely the visual appearance inside the preview.

### Scope and ordering

This is a future enhancement, not a committed requirement for the initial geometry/palette prototype. Build and verify basic repeat behavior first, then test transformations as separate experiments. Preserve the three reference image presets and keep Experiment 001 unchanged.

## Proposed Extension — Surface FX / Realism and Oddities (future)

The long-term ambition is to reconstruct the source tiles **as realistically as practical** rather than produce permanently flat, sterile vector rectangles. The mathematical brick-and-grout construction remains the editable foundation.

### Surface FX / Realism Layer

- Artist controls: brick-only shape irregularity/distortion, edge wear, corner chips, nicks, cracks, pitting/pores, scratches, weathering, grime, mottled color variation, texture intensity, shading and apparent depth.
- Separate **effect target selection**: bricks only, grout only, both, or a global overlay. Distorting a brick must not automatically distort grout.
- Deterministic per-brick variations using a saved **FX seed**, plus a randomize option and reset. Changes should leave the chosen core geometry recoverable.
- Implement later as optional, adjustable non-destructive layers. Vector damage and SVG effects may coexist with Canvas/WebGL textures; distinguish actual vector objects from rasterized rendering.
- Ensure chipped, distorted, or shaded features that cross tile boundaries participate in the same repeat math. Validate seams including corners.
- Allow clean vector, lightly weathered, and heavily distressed render settings, with an original-reference comparison.

### Oddity / Easter Egg Layer

- Optional anomalies: rare replacement bricks, **lizard-shaped brick**, odd silhouettes, etched symbols, tiny easter eggs, and insider jokes.
- Optional spray-paint or stencil graffiti, including editable short phrases like **"Kilroy was here"** or **"NO NUKES"**.
- Controls to consider: **Off / Subtle / Playful / Wild**, rarity/frequency, graffiti density, custom text, seed/randomize, lock individual oddities, reset, and layer visibility.
- Maintain separate **seam-safe** (wrapped/periodic) and **freeform** (deliberately non-seamless) behavior; do not promise seamless export for the latter.
- A special brick inside the repeat cell will appear once *per copy* of the cell. For a truly rare or one-off surprise across a large area, explore larger repeat supercells or a separate final-composition layer.
- AI may later make editable, contextual suggestions for historical details or hidden jokes. The user chooses what to apply.

### Ordering / Status

These are **ideas for future versions**, not blockers for the present standalone geometry/palette prototype. Prioritize correct brick layout, color presets, interactive controls and seamless SVG exports first. Preserve Experiment 001 and all original PNG references unchanged.

## Testing

Verify:

- Horizontal and vertical seamless repetition
- Corner continuity
- Accurate repeat dimensions
- Predictable stagger behavior
- X/Y phase periodicity
- Deterministic colors
- SVG export opens correctly
- No unrelated project files are changed

## Guiding Principle

**Recreate the design system, not merely the pixels.**

Mathematics establishes repeatable structure. SVG provides scalability. Artistic controls provide creative freedom.

AI may eventually help analyze the references and suggest refinements, but the initial geometry engine should work without external APIs.

## Relationship to Experiment 001

Experiment 001 demonstrates simple SVG circuit tile mathematics.

Experiment 002 builds upon those principles by introducing parametric geometry, palette variations, and reconstruction from existing artwork.

Preserve Experiment 001 unchanged.

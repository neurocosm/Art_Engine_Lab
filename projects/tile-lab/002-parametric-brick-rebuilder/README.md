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

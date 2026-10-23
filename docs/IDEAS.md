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

# Bandana Lab — Outsider Accents & Recognizable Micro-Motifs

**Status:** Proposed design exploration; on the shelf for a future Experiment 003 iteration. **No implementation requested.**
**Project:** Art Engine Lab / Tile Lab / Experiment 003 — Bandana Lab
**Companion:** [Shared AI Assistance — Creative Authenticity Control](AI_ASSISTANCE.md)

## Creative vision

Start with a convincing traditional square bandana: intricate paisley, florals, borders, corner ornaments, center medallions, and balanced symmetry. Introduce *small*, carefully integrated non-traditional flourishes that reward a second look.

The artistic moment to aim for: **"Wait — I recognize that!"**

These are not large stickers pasted onto the design. They should share the band's ornament line weight, palette, scale, rhythm, and visual language. The traditional design remains dominant by default. Keep the controls opt-in and reversible.

## Signature control: Outsider Accent Blend

An optional **Traditional ↔ Outsider** 0–100 slider or rotary knob, ideally defaulting to **0** (none) or a clearly marked subtle starting point, distinct from the shared **Historical Accuracy ↔ Creative License** control.

- **0 — Traditional:** no outsider accents; the bandana remains classic.
- **10–20 — Whisper/subtle:** perhaps one hidden symbol, a few stitched-looking lines or a nested geometric flourish.
- **30–50 — Discoverable:** a couple unmistakable tiny motifs while the composition still reads as a bandana.
- **70–100 — Experimental:** outsider iconography can influence more zones and details. High values are *an option*, not the default look.

Blend can influence **frequency, scale, placement and integration** instead of merely opacity. Users should be able to lock some features while changing the blend.

### Independent artist controls (ideas, not fixed UI)

- **Accent family:** None, Kaleidoscope, Fractal, Zodiac Constellations, Planets & Moons, Atom/Energy, Nature Oddities, Mixed.
- **Placement:** border, corners, center medallion, filler field, or scattered subtly throughout.
- **Visibility/recognizability:** hidden, subtle, recognizable, pronounced.
- **Frequency/rarity:** one secret, rare, light, medium. Aim to prevent unintended clutter.
- **Accent scale and line weight:** sized for recognizability at actual bandana/print dimensions, not only when zoomed.
- **Seed/randomize**, lock choices, toggle on/off, and reset. Keep results deterministic for reproducible SVG export.
- **Preview aids:** optionally highlight where the accents live; hide this guide in exported artwork.

An overall style preset (Traditional Paisley, Western, Botanical, Geometric/Art Deco, Psychedelic) should be able to configure defaults while the user overrides individual borders, corners, center, or fillers.

## Recognizable micro-motif families

### 1. Zodiac constellation sprites

Use tiny SVG vector star marks connected by very fine, light lines — a delicately embroidered constellation, not a large star-map illustration.

- Offer the twelve zodiac constellations individually, with optional choice by name/sign and an optional tasteful mix.
- Store recognizable **star positions and line connections** as small structured coordinate/path definitions.
- When labeled as an actual constellation, preserve its identifying configuration as reasonably as possible; if freely rearranged for aesthetics, label it **constellation-inspired** rather than astronomically faithful.
- Keep star dots larger or brighter than connectors; provide per-motif opacity, size and line-weight controls to maintain clarity on dark/light palettes.
- Place as occasional filler clusters, tiny corner discoveries, or a delicate design near the central medallion.
- Avoid turning every filler group into a star chart; rarity is part of the appeal.

### 2. Planetary motifs (especially Saturn)

- A tiny **ringed Saturn** — perhaps the most recognizable icon — integrated inside a floral flourish, paisley interior, corner element or border rhythm.
- Optional crescent moon, sunburst, comet, small orbits, and other planets.
- Prefer original, simple orbital SVG paths and restrained bandana-style linework rather than colorful astronomical clip art.
- Maintain recognizability at print scale without overpowering traditional ornament.

### 3. Atom / Energy symbol

- A familiar stylized atom with intersecting elliptical orbits and a central nucleus; use it as a **symbolic science/energy motif**, not a literal scientifically accurate atom diagram.
- Subtle placements: an inner paisley, center medallion accent, decorative filler, or one tiny border interruption.
- Let line style match surrounding petals, veins, and swirls. Tiny dots on orbit paths are optional.

### 4. Kaleidoscopic accents

- Small mirrored radial stars or crystalline fragments, optionally nested within a rosette or medallion.
- Keep the classic overall symmetry intact; use controlled little pockets of more complex symmetry.

### 5. Fractal-inspired accents

- Recursive curls, branching leaves, self-similar petal or paisley interior detail.
- A depth/detail slider may be useful; keep geometry lightweight for SVG performance.
- Clearly distinguish a mathematically generated fractal from merely **fractal-inspired** self-similar decoration.

### 6. Nature oddities / Easter eggs

- A tiny lizard, beetle, moth, mushroom, or other recognizable mini-motif — the bandana counterpart to Tile Lab's surprise *lizard-shaped brick*.
- Rare, integrated, and optionally hidden; not every design needs an oddity.

## Examples of the intended result

- Classic red/white paisley at **10% outsider**: a tiny Saturn embedded in one corner flourish.
- Navy/cream design at **15%**: one recognizable zodiac constellation drawn from dots and faint hairlines between floral fillers.
- Black/white bandana at **12%**: an ornamental atom symbol worked subtly into the central rosette.
- Traditional floral at **20%**: minute kaleidoscopic details or self-similar curls inside a few motifs, without changing the overall traditional silhouette.

## Relationship to existing controls

- **Historical Accuracy ↔ Creative License** (shared AI feature): controls whether suggestions follow real historical constraints or allow imaginative invention.
- **Traditional ↔ Outsider Accent Blend** (Bandana visual feature): controls how much nontraditional iconography appears, independently of historical correctness.
- **Ornament Style / Border / Corner / Center / Filler**: choose the composition's base vocabulary. Outsider motifs should not replace these selections unless the artist explicitly chooses it.

An accurate traditional bandana may still have one intentionally anachronistic micro-motif; the tool should explain that distinction instead of conflating the two sliders.

## Rendering and print constraints

- Prefer actual editable **SVG shapes/paths/symbols** (not raster "sprites"); here "sprite" means a tiny reusable decorative icon. SVG `<symbol>`/`<use>` is a possible future technique.
- Reuse structured motif definitions and theme-driven color/line parameters.
- Respect symmetry and ornamental balance, but permit intentional asymmetry for a single surprising detail.
- Maintain enough contrast for tiny stars and hairline connectors at real export/print size; optional preview at actual output size.
- Keep accents optional, removable, and independently editable. Do not silently overwrite the original bandana artwork.
- Classic square bandana composition is **not** itself the same as a seamless textile repeat. A later seamless-repeat mode must wrap accents correctly; otherwise identify them as one-off placement layers.

## Proposed sequencing — not a development mandate

1. Preserve and refine the working Experiment 003 classic SVG bandana composition.
2. Add real selectable ornament *families* for borders/corners/center/fillers.
3. Introduce **Outsider Accent Blend** with one minimal family (e.g. Saturn, atom or one constellation) and explicit placement.
4. Expand motif library only after subtlety, recognizability, export and visual hierarchy are verified.
5. Optionally connect AI for suggestions once a secure shared service exists; AI must not be required for manual use.

**Open questions:** exact default blend value, which zodiac connection conventions to use, final preset designs, support for alternate placements, whether to allow many simultaneous accents, and how to store user presets.

**No code, API calls, external assets, or architecture decisions are authorized by this document.**

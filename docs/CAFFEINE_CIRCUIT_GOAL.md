# Caffeine Circuit — Tile Lab design goal

**Status:** Planned / concept approved for documentation; no application or procedural artwork implemented yet.  
**Home:** Art Engine Lab → Tile Lab (independent future experiment).  
**Origin:** The phrase “Caffeine Circuit,” coined during a VR zombie-shooter session, inspired a hybrid of caffeine molecular notation and electronics/PCB artwork.

## Creative brief

Make a striking, scalable, editable graphic in which a **caffeine molecule** anchors the center of a stylized **printed circuit board**. Place a **simple, recognizable transformer schematic/coil** at the heart of the composition. Circuit traces branch into the surrounding field, joined by sparse pads/vias and occasional **resistors, diodes, capacitors, and other electronics symbols**. It should read as an integrated electronic design, not a collage of unrelated stickers.

The central molecule and transformer are the hero. Preserve an uncluttered silhouette, readable chemical marks, coherent linework, and intentionally generous negative space around that hero.

### Centerpiece — non-negotiable

- **Complete caffeine structure**: reference the real molecular formula **C₈H₁₀N₄O₂** (1,3,7-trimethylxanthine), with the correct fused rings, atoms, carbonyls, and three N-methyl substituents. In future precise vector versions, validate against a trusted chemistry reference rather than blindly tracing generative-image approximations.
- **Transformer inside the center**: use a legible line-art transformer symbol or paired coil/laminated-core motif. It is an **artistic overlay or inset** in unused visual space, **not a replacement for or interruption of chemically necessary bonds or labels**.
- The center should retain priority even as styles, palettes, line density, and underlying repeating arrangements change.
- Any central chip/coffee-bean icon from the **earliest brainstorming image** is historical exploration; the **transformer replaces it** in the preferred design.

### Surrounding electronics

- Start with a printed-circuit visual language: crisp routed traces, intentional 45°/90° corners, vias, small through-hole pads, occasional resistor zigzags/banded resistors, diode and capacitor symbols, and optional grounds or terminals.
- **Background circuit density: 85% of the earlier denser reference (about 15% fewer secondary traces/components).** This reduction applies to supporting circuitry **only**, not the caffeine structure or transformer.
- More negative space and restrained glows are preferable to uniformly bright or overfilled circuitry. Detailed components should be accents, not noise.
- Favor balanced or approximately symmetric visual rhythm, but permit small controlled asymmetry for a natural circuit aesthetic.
- Treat the wiring as **decorative schematic/PCB-inspired art**, not a claimed electrically functional circuit. If paths visually cross without connecting, depict intentional separation/crossover.

## Style forks & palettes

Make palette independent of geometry so any design can be recolored without destroying its editable SVG structure. The following are *candidate palette tokens*; exact shades and glow tuning are artist-adjustable.

### A. Original “Neon Caffeine” (initial exploration)

- Black or near-black background; vibrant cyan/turquoise, electric teal and lime-green traces and nodes.
- Central molecule luminous and high-contrast; selective glow, science-meets-cyberpunk aesthetic.
- This was the first visual direction, initially with a microchip/coffee-bean accent that was subsequently swapped for the transformer.

### B. “Arizona Dusk” colors — **not Arizona imagery**

- Deep plum/indigo base with **burnt orange, copper, golden amber, magenta/dusty pink, violet and restrained teal**.
- Suggested working swatches: near-black plum `#15101E`, indigo `#231A40`, burnt orange `#E76B2C`, copper `#B94E3D`, amber `#F1B45C`, pink/magenta `#C94C87`, teal `#27A7A7`.
- **Explicit exclusion:** no sunset disks, mountains, mesas, cacti, sand, skies, landscapes or desert motifs. “Arizona dusk” describes **only the color atmosphere**.
- Keep the same scientific and electronic geometry as the cyan design.

### C. Patriotic “Midnight Americana” colors

Maintain the black/gray base and use red-white-blue **families**, not a single shade of each:

| Role | Color names and candidate hex |
| --- | --- |
| Background | Near black `#090C15`; midnight blue `#111E42` |
| Reds | Signal red `#E53945`, crimson `#BF2035`, burgundy `#741C32` |
| Blues | Electric blue `#3475E5`, navy `#203F83`, midnight `#111E42` |
| Neutrals | Warm white `#F4F1E9`, silver gray `#A7ACB8`, gunmetal `#444B5A` |

Suggested placement:
- Warm-white / ivory molecule bonds and labels as the focal point.
- Transformer with metallic silver/gunmetal frame and optionally **red and blue coil windings**.
- Primary/background traces alternate crimson/burgundy and electric/navy blue; silver tracks and component highlights break up the saturation.
- Black-to-midnight base and **selective** glow preserve negative space.
- Patriotism comes through **color**, not literal flags, stars, stripes or other national symbols.

Preserve **all three** viable intensity presets:
1. **Vintage Electronics** — muted burgundy, navy, weathered silver, warm white; minimal glow.
2. **Midnight Americana** — balanced red/blue, warm-white molecule, metallic components; recommended midpoint.
3. **Patriotic Voltage** — brighter signal red and electric blue with more pronounced luminous accents.

### D. UK / Union Jack-inspired **fork**

- Use the **same broader patriotic red, white/ivory, navy/electric-blue, black and gray palette** and the **same caffeine-plus-transformer center**.
- Subtly arrange **supporting PCB trace routes** into a composition influenced by the Union Jack’s **vertical and horizontal cross plus opposing diagonal saltires**.
- The flag influence should be evident in **routing rhythm and crisscross structure**, not require a pasted or literal Union Jack. Let traces, resistors, diode symbols, vias, and separated rails create the geometry.
- Retain the **85% background density**, readable, complete central chemistry, and unobstructed transformer.
- Keep crossings electrically legible as decorative artwork; avoid accidental junctions or cover-ups.
- Offer a future **Flag Geometry Influence / Crisscross Strength** parameter from subtle to more recognizable, default subtle. Never force this topology onto the other palette variants.

## Proposed artist controls (future, not yet built)

- **Palette**: original neon / Arizona Dusk / patriotic, with individual swatches and custom colors; intensity presets for the patriotic fork.
- **Layout/fork**: regular PCB vs UK-cross-inspired composition. A selection should not overwrite the other fork.
- **Secondary density**: default **85%**, with 100% representing the previous busier concept; preserve protected centerpiece geometry regardless of density.
- **Glow/brightness**; background black-to-plum/navy tone; line widths; metals/texture intensity.
- **Transformer style**: simple symbolic coils vs understated metallic coil housing; center remains protected.
- **Symmetry/structure** and **Union Jack influence strength**, where applicable.
- **Deterministic seed** for optional peripheral trace and component variations so the same settings reproduce the same design.
- **Repeat presentation**: standalone square emblem and a repeat-aware tile preview, with independent repeat/phase controls when appropriate.
- Reset, export, palette preview, and visible controls alongside artwork (avoid excessive scrolling).

## Build approach & validation

1. **Prototype as standalone HTML/CSS/JavaScript + procedural SVG**, consistent with Tile Lab's early experiments; keep molecular/transformer layers distinct from supporting PCB layers, palettes, and effects.
2. Use grouped and named editable vector primitives for caffeine, transformer, routing, components, and optional decorative overlay. Keep texture/glow effects distinguishable from core geometric vectors.
3. Create a **single motif/emblem preview** and a **3×3 repeat preview**. If marketed as seamless, the exported repeat unit must have valid wrapped edges/corners, with an explicit seam diagnostic view; otherwise label it an emblem or intentionally framed composition rather than promising a seamless tile.
4. Compare each of the four directions at 85% density. Verify that changing density does not remove a bond, chemical atom, label, or transformer detail.
5. Check molecular structure against a trustworthy chemical diagram; inspect text readability at normal/print scale, line weight, component spacing, color contrast, and crossing clarity.
6. Export editable SVG first; optional raster PNG previews later. Preserve repeat geometry and consistent color tokens. Do not assert that generated screenshots are editable vector source.
7. Only add source-owned or properly licensed reference assets. Earlier images were generated in the ChatGPT brainstorming conversation and are **visual concepts**, not committed source files or verified chemical blueprints.

## Suggested milestones / acceptance criteria

- [ ] Document the four looks and protect the central molecule + transformer as invariant geometry.
- [ ] Build an **accurate** and legible caffeine SVG centerpiece with transformer as inset/overlay.
- [ ] Generate circuit traces and occasional electronic symbols, with a verifiable **85% default density**.
- [ ] Implement interchangeable palette and intensity presets, including custom colors.
- [ ] Implement the UK-inspired route topology as a separate reversible branch/preset.
- [ ] Supply single-view and repeat previews, and validate actual seams when claiming seamless tiling.
- [ ] Export source-preserving SVG and test multiple scales, text visibility, and layer toggles.
- [ ] Capture before/after comparisons and known limitations, per Art Engine Lab's workflow.

## Scope boundary

**Goal/design record only for now.** Do not take this as authorization to rewrite the existing 001 circuit prototype, 002 brick research, or 003 Bandana Lab; this may eventually become its own independent Tile Lab experiment. No API, paid image generation dependency, or production app is required to validate an initial procedural SVG proof of concept.

# FACET LAB — Design Session Notes

**Session:** 2026-10-27 (continued into 2026-10-28)  
**Project:** Art Engine Lab → FACET LAB / 01  
**Category:** geometric silhouette and contour editor; first specimen: Tele-style **bass** body  
**Principle:** *Mathematics provides precision. AI assists interpretation. The artist retains creative control.*

## 1. Creative purpose

Take a familiar, traditional Telecaster/T-style body silhouette and **reimagine its outer shape** in a controlled, geometric, low-polygon visual language. Preserve enough of the original's asymmetry, stance, and mass to remain recognizably Tele-inspired.

The user likened the intended look to running the outline through an “8-bit” or **“12-bit”** art program; this is a playful metaphor for a *slightly polygonized contour*, **not actual pixelated raster steps**. The desired result is refined and architectural rather than Minecraft-like, crude, or excessively sci-fi. Begin with the outline. The immediate aim is **exploration and visual feedback**, not detailed manufacturing decisions or a full instrument design.

### First-session key direction

> Replace the classic smooth body perimeter with intentional straight segments; make the bottom broad and octagon-ish, then adapt the same idea more carefully in the complex upper half.

**Do not lose the underlying Tele identity.** At the other extreme, don't make facets so timid that the design still looks unchanged.

## 2. Original silhouette observations

Original reference: simplified, single-color, front-facing Tele-style body silhouette on black. Features:
- **Upper bass-side shoulder (image left):** broad, rounded, full, no treble cutaway; gently transitions toward the neck-pocket plateau.
- **Upper treble-side horn and cutaway (image right):** prominent, deep U-like scoop; needs careful shorter sections because of tighter radii and potential fret-access implications.
- **Neck pocket/top center:** straight-sided, squared notch; an existing geometric anchor, but neck design and fit are **not** part of v01.
- **Waist:** softly narrowed, not an extremely pinched hourglass; preserve its balance and recognizable shape.
- **Lower bout:** wide, substantial, almost a rounded rectangle; the largest opportunity to replace soft arcs with strong diagonal edges and a flatter bottom chord.
- **Overall:** distinct asymmetry; avoid casually mirroring left and right.

### Proposed distribution of segments

- **Lower bout:** long, deliberate diagonal/straight facets; octagon-inspired transitions at lower corners, flatter center-bottom section.
- **Lower sidewalls/waist:** clean transitions between the wide lower body and narrow middle; avoid accidental jagged notches.
- **Upper bass-side shoulder:** medium-length facets with enough visual generosity to retain the traditional silhouette.
- **Cutaway/upper horn:** fewer large mistakes, **more short facets** around the tight inner scoop; don't force the same segment lengths used at the bottom.
- **Neck-pocket lip:** leave obvious straight geometry; physical pocket measurements to follow if the project becomes a fabrication model.
- **Edges:** a subtle continuous bevel/chamfer is desirable, so light can emphasize the polygon form while making the real body less sharp to handle.

This is an **asymmetric, scale-sensitive approximation strategy**, not a strict rule requiring equal segment lengths or exact multiples of 22.5°/45°.

## 3. Decisions and working assumptions

**Confirmed design direction:**
- An **electric bass** body, not a six-string guitar body.
- **Tele-style** outline as the original inspiration.
- A medium **“12-bit” low-poly** treatment is the initial sweet spot; compare milder and bolder variations later.
- **Both upper and lower sections** use geometric contours; upper segments should be selected more carefully because they span smaller curves.
- **Beveled edges** are visually desirable. Begin with an adjustable 2D representation.
- First design round is **body-only**. No neck or headstock work.
- Keep a **clean, uncluttered front face** in mind.
- **Rear-routed electronics** is the current preferred direction if the body eventually receives hardware.
- This becomes a **self-contained Art Engine Lab experiment**, with broader silhouettes as an eventual use case.

**Tentative, not locked in:**
- Material: **maple** was mentioned as a visual direction, possibly paired with a maple neck. The user also considered modifying an existing wood blank **or** 3D printing. No material/production choice is final. **Maple is not inherently light**; mass depends on species, dimensions and density.
- Pickups: user described **two split-coil pickups** for a bass; likely two P-style split-coil assemblies, but exact topology, placement, and wiring are undecided. Do not add pickups to the initial visualization.
- Pickguard: **undecided**, with a possible clean pickguard-free face.
- Controls, jack, bridge, precise neck fit, 3D body thickness, belly/forearm carve, strap positions: **not part of first design stage**.

## 4. What we learned from the earlier AI conversation

The earlier assistant repeatedly shifted toward manufacturing, hardware, neck dive, 3D printing, control placement, body sculpting and questions about future choices **before the user could view a single adjusted silhouette**.

That sequence was frustrating. **The appropriate FACET LAB workflow is:**
1. Make a *visual* body silhouette variation.
2. Inspect the result together.
3. Adjust facets and bevels through immediate controls.
4. Only then discuss any construction constraints that actually bear on a chosen visual design.

An attractive AI rendering of a pale maple, chamfered, geometric Tele-like body inspired the interactive work. This rendering is **concept art**; it does not establish a CAD-compliant physical model or an identical vector trace.

## 5. FACET LAB / 01 — current interaction contract

The standalone HTML/CSS/JavaScript application implements an SVG drawing in the browser with:
1. **Bevel slider:** visual ridge inset from 0 to 40 *drawing* units. Not millimeters and not 3D thickness.
2. **Subtle, Balanced, Bold** presets: different curated arrays of outer polygon vertices.
3. **Maple, Line Art, Blueprint** appearances: same underlying contour; the maple mode uses **SVG** gradient/stroke patterns rather than raster photo.
4. **Show contour vertices** diagnostic.
5. **Reset** and **editable SVG export** (no debug markers in export).
6. No backend, no dependencies, no telemetry and no external AI service.

The contour is currently **hand-specified from observation**, not a mathematically validated trace of the original uploaded image. The inset is a 2D mitered-line geometry demonstration with clamping for extreme joins; deep inset self-intersections should be considered an unresolved limitation. Export captures the illustration, **not** a guaranteed watertight manufacturable object.

## 6. Broader FACET LAB idea — proposals

The guitar is our *first specimen*, not the tool's permanent limit. Explore:
- Importing SVG/raster silhouettes; optional auto-trace **with editable human review** rather than hidden black-box decisions.
- Point dragging, node insertion/removal, local segment length and density, optional fixed-angle snaps (e.g., 15°, 22.5°, 30°, 45°), straight-line preservation and corner joining.
- Side-by-side comparisons: original/mild/medium/aggressive.
- Shape interpolation and reversible operation history.
- A separate **bevel width** vs **3D bevel depth** distinction; true multi-plane body surfaces only if/when needed.
- Symmetry options for shapes that benefit; **preserve the Tele's intentional asymmetry by default**.
- Named presets, reusable vector contours, export/import of SVG and parameter JSON.
- Eventually measured dimensioning, pickup/cavity keep-out zones, ergonomic checks, CNC/DXF or mesh export, and material simulation; these require independently specified geometry and real validation.

**Not presently decided:** importing tech, save-state storage, 3D modeling approach, CAD tooling, hosting, framework, file formats beyond SVG, or relationship to shared AI helper. Do not treat proposals as requirements.

## 7. Suggested next visual experiment

Display **three simultaneous contour studies** derived from the same editable original:
- **Mild:** nearly familiar Tele, with restrained polygon corners.
- **Balanced:** obvious but elegant low-poly silhouette; promising primary direction.
- **Aggressive:** bolder long edge planes, a diagnostic extreme to compare against.

Review especially the *lower-bout octagon*, the cutaway's hand-clearance appearance, horn proportions, and whether side facets preserve the body's visually grounded stance. Make changes in response to the artist's eye **before** choosing instruments, hardware or manufacturing techniques.

## 8. Fabrication guardrails (for later)

- An SVG silhouette alone says nothing about neck-pocket dimension, string scale, rout clearances, bridge alignment, structural strength, balance, weight or strap locations.
- The original silhouette geometry may have distorted proportions and cannot be assumed 1:1.
- True chamfer width/depth, corner radii, comfortable contact surfaces, and valid 3D-print joining/infill specifications are separate engineering tasks.
- No automatic claim that a printed plastic guitar body will be adequately rigid or balanced; it requires structural assessment.
- Preserve an unmodified reference and version design changes separately.

## 9. Design language in one sentence

*A Tele-style electric bass body whose iconic asymmetrical silhouette is retained while its organic curves become crisp, intelligently scaled straight facets, with an adjustable perimeter chamfer that makes the form feel like a beautifully resolved low-poly object.*

---

**Provenance:** distilled from the user's supplied silhouette, the quoted Chrome AI conversation, and subsequent ChatGPT FACET LAB image/app design discussion (October 27–28, 2026). Distinguishes confirmed intent from speculative options. No proprietary 3D model or production-ready CAD file is implied.

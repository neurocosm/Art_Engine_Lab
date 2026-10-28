# FACET LAB — Geometric Silhouette & Contour Studio

**Art Engine Lab independent experiment · FACET LAB / 01**  
**Status:** working, offline, self-contained SVG prototype; exploratory body design, **not** a fabrication drawing.

## Run it

Open [index.html](index.html) directly in a browser (Chrome, Firefox, Edge, Safari). No server, installation, build process, packages, paid services, AI calls, or internet connection required.

**What works in v01:**
- Live **bevel width** slider from 0–40 drawing units. At zero the shape has no inset chamfer band.
- **Subtle / Balanced / Bold** contour presets with different point density.
- **Maple / Line Art / Blueprint** drawing modes.
- Optional **vertex markers** for inspecting geometry. These are omitted from exported SVG.
- **Reset** and **Export editable SVG**. Export includes vector polygons and SVG gradient/pattern fills; it is not a raster screenshot.

The visual language is a **Telecaster-inspired bass body**, faceted like a restrained “12-bit” / low-poly object. The broad lower bout uses larger angled segments; the upper shoulder and deep treble cutaway retain smaller and more intentional transitions.

**Try:** select **Bold → Line Art** and drag the bevel slider from zero upward, then compare to **Balanced → Maple**.

## What is—and is not—being modeled

The outline is a **manually defined approximate vector interpretation** of the silhouette discussed in the October 27, 2026 design session. This first version does **not** automatically trace uploaded images or create an exact dimensioned Telecaster body. Each contour preset uses a set of straight-line vertices. The bevel control offsets an inner contour to create a polygonal perimeter band with light/shadow tones. It is a **2D visual chamfer illustration**—not a physical 3D cut depth or a guarantee of consistent manufactured bevel faces.

“12-bit” is an **aesthetic shorthand**, not a bit-depth setting or promise of 22.5° / 45° constraints. The line-art and blueprint modes are fully vector; maple mode uses SVG gradient and procedural stroke-line pattern approximations for wood. It does not embed the photorealistic AI image.

There is **no neck, headstock, fretboard, pickups, strings, bridge, jack, pickguard, or control system** in v01. This is deliberate: **silhouette first, engineering later**.

The exported drawing needs validation and dimensioning before CNC, woodworking, routing, 3D printing or physical assembly. Inset algorithms for concave polygon shapes may require more robust joins/overlap handling as bevel widths increase.

## Design history & future directions

Read [DESIGN_NOTES.md](DESIGN_NOTES.md) for the user's complete design intent, the original silhouette analysis, discussion decisions, open questions, and an ordered roadmap. The core creative objective is to keep the iconic T-style stance recognizable while converting curves into crisp, deliberate geometry—not to create a square pixel-art parody.

### Future FACET LAB scope (proposed, not implemented)

FACET LAB could later grow from the initial bass body specimen into a reusable silhouette editor for logos, instruments, furniture, shapes, and other graphic outlines:
- Import original raster silhouettes or SVG paths and **manually review** a traced contour.
- Move/add/delete individual vertices; refine local segment density and angle snapping.
- Adjustable chamfer width and optional geometric corner treatments, separately from a true 3D bevel.
- Comparison view: original, mild, medium, bold; overlay and before/after.
- Save/load named experiments, undo/redo, SVG/JSON presets; potentially DXF or CAD-friendly export after dimensional validation.
- Symmetry, constraints and scale only where sensible. Maintain intentional Tele-style asymmetry.
- Optional parametric 3D body model at a later, separately engineered stage.

**Do not** bolt this into a combined Art Engine Lab shell yet. It is intentionally independent.

## Project files

- [index.html](index.html) — self-contained interactive app and vector geometry.
- [DESIGN_NOTES.md](DESIGN_NOTES.md) — decisions, inspiration, constraints, and next experiments.

## Verification checklist

- [ ] Open locally in at least one desktop browser.
- [ ] Bevel at zero removes the shaded band; increasing it changes the inner ridge.
- [ ] All three detail presets change point counts and silhouette.
- [ ] All three display modes update without reloading.
- [ ] Vertex toggle shows points in preview; an exported SVG does **not** include debug circles.
- [ ] Reset returns to Balanced / Maple / 16 / markers off.
- [ ] Export a nondefault configuration; reopen the downloaded SVG and compare its contour and fill with the preview.
- [ ] Inspect narrow-screen layout and keyboard focus.

These items are **manual acceptance checks**, not claims of automated test coverage. Do not mark them passed without actually running them in a browser.

## Source/provenance

The first specimen is derived from a body silhouette supplied in the ChatGPT design conversation on October 27, 2026. An AI-produced *photorealistic maple concept rendering* informed the aesthetic; it is not the app's vector geometry. The original image and high-resolution rendered study are deliberately **not committed** as binary repository assets. The shape coordinates live in the script and may be edited without those images.

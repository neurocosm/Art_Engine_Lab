# Tile Lab

Independent experiments in seamless repeat mathematics and artist-facing adjustment controls.

## 001 — Procedural SVG Circuit Tile

Open [the experiment](001-procedural-svg-circuit-tile/index.html) in a browser. It uses plain HTML, CSS, JavaScript, and SVG, with no installation or build step. Opening the HTML file directly works for the editor and export.

For browser tests, serve the repository from its root:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Navigate to `/projects/tile-lab/001-procedural-svg-circuit-tile/index.html` on that server. Open `tests.html` in the same directory to run the browser checks; wait for **ALL CHECKS PASSED**. The test page needs HTTP because it inspects a same-origin iframe.

### What to try

1. Compare the enlarged single cell with the 3×3 preview.
2. Move X and Y independently. Enable tile boundaries and follow traces crossing them.
3. Compare phase 0 with 100: one complete period produces the same artwork.
4. Try 50/50 and 99/1, watching the edges and the corners.
5. Reset phase. The boundary checkbox retains your preference.
6. Export SVG at a nonzero phase, reopen the downloaded file in a browser, and compare it with the single-tile view. Export never includes guide lines.

### How the mathematics works

The tile has a `100 × 100` coordinate system. A motif is repeated at translations `(100i, 100j)` for integers `i` and `j`. All copies receive the same phase `(px, py)`, giving `(x + 100i + px, y + 100j + py)` for each point of the motif.

Adding 100 to either phase just selects a neighboring identical copy. The code therefore normalizes phase with `((value % 100) + 100) % 100`. This is a translation of the whole periodic field; it does not move one motif independently or change the repeat spacing.

An SVG `<pattern>` fixes the cell boundaries. Inside it, neighboring motif copies are translated and clipped to the cell. Those copies matter: simply translating one clipped drawing would lose the parts that need to wrap around. In this example the geometry, including strokes, lies within `[-2, 102]` on each axis. After phase normalization, indices `-2` through `1` cover every copy that can intersect the cell. Revisit these bounds if you enlarge the motif or its strokes.

The paths exiting the left/right edges have matching horizontal continuations; the paths exiting top/bottom have matching vertical continuations. The same periodic construction wraps pads and other geometry when phase moves them across an edge or corner. Both previews and the export use the same SVG generator, with distinct pattern IDs for the two inline previews.

### Files and validation

- `index.html`: the complete experiment, including inline CSS and JavaScript, accessible controls, motif geometry, periodic copies, and SVG download. Inline assets allow HTML-only previews to run without resolving sibling file paths.
- `tests.html`: real-browser checks with no test framework or dependencies.

The tests rasterize SVG **only for pixel comparisons**; the artwork and export remain vector. They compare the 3×3 view against repeated exported-tile pixels at five phase settings, check exact full-period equivalence, and compare a nonzero phase with a wrapped pixel translation of the original field. They also check slider updates, reset, guide visibility, and standalone SVG parsing. Tile/preview comparisons allow at most one channel level of rounding difference. The translated-field check allows two levels (out of 255) because Chromium can round translated curve coverage differently; the observed maximum was two. The test runner reports failures visibly; loading the page alone is not a passing result.

Manual checks remain useful: inspect continuity at several zoom levels, operate controls with the keyboard, check a narrow screen, and reopen an actual downloaded SVG. Mathematical periodicity does not guarantee attractive spacing or identical anti-aliasing in every SVG viewer.

### Limits and next experiment

This is a procedural straight-grid prototype, with fixed geometry and palette. It has no raster import, half-drop repeats, PNG export, AI, or electrical-circuit semantics. It does not imply print readiness. There is no external reference image; the original procedural geometry is in the script inside `index.html`. The single-cell and repeated views provide the live visual comparison.

For a next small experiment, edit one path or pad, predict what will happen at its boundary, and rerun the checks. Keep phase, motif relocation, and changes to the repeat lattice conceptually separate.

### Embedded preview troubleshooting

The editor is now one standalone HTML file. An HTML-only iframe previously showed empty preview containers when it could not resolve the relative `style.css` and `app.js` URLs. CSS and JavaScript are inline now, so sibling asset paths are no longer needed. The embedding host must still permit JavaScript and SVG. A host Content Security Policy, sanitizer, or iframe without `allow-scripts` can prevent rendering; application code cannot override those restrictions. Downloads additionally require the host to permit downloads. If an embedded preview reports a host error, compare against the page served over HTTP in a regular browser.

# Decisions, Assumptions, and Open Questions

Last updated: 2026-10-26.

## Agreed directions (as currently understood)

- Prefer **one GitHub monorepo** for multiple related art-tech subprojects; each can be developed independently.
- Use **ChatGPT Projects** for creative conversation history and project context; explicit repository docs will provide Codex with durable, versioned instructions.
- The project begins as a learning and experimentation space, rather than a rigid specification for one production application.
- Existing raster artwork and seamless tiles are important learning inputs.
- Seamless tiling should include **mathematical repeat logic plus artist-facing X/Y and other adjustments**.
- Show the repeated pattern while tuning it; a correct single tile may still look aesthetically awkward.
- AI is a desirable assistant for future image understanding and reconstruction, rather than a replacement for manual control.

## Experiment 003 — Bandana Lab: confirmed foundational decision (2026-10-26)

- **Primary output:** a **borderless, continuous, seamless ornamental field** inspired by the spirit of traditional bandana art (paisley, curls, florals, vines and fine filler ornament)—**not** an array of copied, framed square bandanas.
- The repeat cell remains real mathematically, but its edges and repeat boundaries **must not appear as a visual frame** in the finished design. Treat seam correctness as testable math and visually concealed repetition as a separate artistic goal.
- The original Codex square-bandana composer is useful as a prototype/reference. Keep it intact while transitioning incrementally; framed-composition mode may remain optional, **not default**.
- Reorient controls toward organic flow, motif families, density, clusters, size, orientation and seamless preview instead of outer/inner borders and fixed corners/medallions.
- **Artwork View** shows an uninterrupted 3×3 or 5×5 pattern; optional **Engineering View** reveals repeat cells and seam diagnostics, never included in clean export.
- Outsider Accent Blend and celestial/scientific micro-motifs remain proposed options and must not disrupt the underlying seamless repeat field.
- **Rationale:** The user wants a seamless field whose traditional bandana vocabulary flows beyond any frame; a grid of discrete bandana squares misses that creative objective.
- **Full direction:** [Bandana Lab — Borderless Seamless Ornament](BANDANA_LAB_FOUNDATION.md).

## FACET LAB — Geometric silhouette studio (2026-10-27)

- Add a **self-contained** FACET LAB experiment in `projects/facet-lab/`, with the Tele-style **electric bass** silhouette as its first subject, not a hard-coded limit on future subjects.
- Confirmed first-stage goal: preserve a recognizable, asymmetrical T-style outline while replacing smooth contours with intentionally scaled straight-line facets; use broad octagonal-inspired segments on the lower bout and shorter, more careful transitions above.
- A **visual** adjustable perimeter bevel, 2D SVG geometry, and multiple contour/detail presentations precede pickup layouts, dimensional CAD and manufacturing decisions.
- Preserve an uncluttered front and treat rear-routed electronics as a preferred later direction. Pickguard, pickup layout, material, neck, 3D-printing or cutting approach remain open.
- **Implementation:** prototype and full session notes at [FACET LAB](../projects/facet-lab/). The initial app is a shape study, not a true 3D beveled part or production-ready template.
- **Rationale:** Make and compare silhouette experiments immediately rather than delaying visualization with premature technical decisions.

## Proposals only — not locked in

- Current folder names and number of subprojects.
- A unified application that chooses SVG/Canvas/WebGL per layer.
- Automatic repeat-cell extraction and AI layer segmentation.
- Print workflows and export targets beyond initial SVG/PNG.
- Choice of language, UI framework, libraries, algorithms, hosting, or AI provider.

## Open engineering questions

1. Should the first prototype prioritize importing existing tiles or constructing procedural ones?
2. How should raster textures be retained within otherwise vector exports?
3. Which repeat families are in scope for v1?
4. Which metrics will distinguish guaranteed seam continuity from visual quality heuristics?
5. How will imagery, fonts, licenses, and high-resolution source files be managed?
6. What data schema, if any, should represent art layers between engines?

## Change log

- **2026-10-23:** Established monorepo idea, raster reconstruction learning goal, future AI-assisted art toolbox, and distinction between mathematical seamlessness and artistic X/Y adjustment.

- **2026-10-26:** Confirmed Experiment 003's primary target as continuous borderless repeat artwork; reframed earlier classic square composition as an optional secondary reference. This is a design decision, while the exact geometry algorithms and controls remain open.

Add future decisions here with date, rationale, consequences, and whether the choice is reversible.

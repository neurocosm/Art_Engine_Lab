# Decisions, Assumptions, and Open Questions

Last updated: 2026-10-23.

## Agreed directions (as currently understood)

- Prefer **one GitHub monorepo** for multiple related art-tech subprojects; each can be developed independently.
- Use **ChatGPT Projects** for creative conversation history and project context; explicit repository docs will provide Codex with durable, versioned instructions.
- The project begins as a learning and experimentation space, rather than a rigid specification for one production application.
- Existing raster artwork and seamless tiles are important learning inputs.
- Seamless tiling should include **mathematical repeat logic plus artist-facing X/Y and other adjustments**.
- Show the repeated pattern while tuning it; a correct single tile may still look aesthetically awkward.
- AI is a desirable assistant for future image understanding and reconstruction, rather than a replacement for manual control.

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

Add future decisions here with date, rationale, consequences, and whether the choice is reversible.

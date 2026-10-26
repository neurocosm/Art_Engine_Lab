# Shared AI Assistance — Creative Authenticity Control

**Status:** Concept / proposed shared capability; not implemented.
**Scope:** All Art Engine Lab experiments, including Tile Lab, Raster Rebuilder, Render Lab, AI Composer, and Untrue Band Studio.

## Vision

Each creative application may eventually offer an optional **Ask AI** assistant that knows the current experiment, the artist's intent, and (with the user's approval) relevant canvas layers or reference images. AI acts as a creative collaborator: it can explain, research, brainstorm, and suggest editable artwork, but it does not silently redesign or overwrite work.

This is **one reusable capability**, not a separate API implementation in every project. Choosing a particular model provider, framework, or service remains an open decision.

## Signature control: Historical Accuracy ↔ Creative License

A single slider or rotary knob changes how much the assistant favors verifiable period conventions versus playful invention. **The setting affects content constraints, not the artist's freedom or the general quality of ideas.**

| Setting | Intent | Example for a 1970s amplifier-inspired circuit tile |
| --- | --- | --- |
| **0 — Historically Accurate** | Prefer era-plausible components, markings, typography, materials, language, and layout. Verify specific factual claims when evidence matters. | An era-plausible TO-3 transistor, resistor banding and PCB silkscreen conventions. |
| **50 — Balanced** | Keep the visual language recognizable while allowing fictional labels, tasteful exaggeration, and small inside jokes. | A believable-looking board with a fictional "Stereo Phase Alignment" module. |
| **100 — Creative License** | Invite alternate histories, absurd components, retro-futurism, fictional venues and playful engineering humor. | An invented time-bending audio module advertised in a 1970s electronics-store-style flyer. |

**Important:** This is a *creative direction preference*, not a mathematical accuracy score or a guarantee of truth. Historical facts, fictional inventions, and unverified claims must remain distinguishable at every setting. Even at 0, a fake band can remain fictional while using an era-appropriate look.

A future two-axis version might independently control **historical plausibility** and **wildness/humor**; do not commit to that UI yet.

## How it could work

1. The artist chooses the current project, era, medium, and intent (e.g., "technical nostalgia with subtle geek jokes").
2. The artist optionally supplies a prompt and approves sharing the relevant image or SVG layer context.
3. The shared AI service returns **labeled** historical references and/or invented ideas, plus explanations.
4. Where useful, the service may propose structured, editable changes: SVG shapes, palettes, text, motifs, layer parameters, or layouts.
5. The application previews proposed changes; **the user accepts, edits, or rejects** each one. Original artwork remains recoverable.

Potential controls: slider/knob, reset to balanced, "explain this suggestion," "more period-authentic," and "make it weirder." These are UX ideas, not requirements.

## Example prompts

- **Tile Lab:** "What electronics components used in a 1970s hi-fi amplifier would look nostalgic and interesting woven into this seamless circuit tile?"
- **Untrue Band Studio:** "Invent a plausible 1978 progressive-rock tour shirt, with an original fake band, a fictional arena, and a few technically nerdy Easter eggs."
- **Raster Rebuilder:** "Which details in this poster should be faithfully reconstructed as vectors, and which could be artistically reimagined?"
- **Render Lab:** "Show me an era-appropriate effect and an experimental alternative, with trade-offs for scalable output."

A movie-style imaginary component in a nostalgic electronics-store flyer is a good **creative-license illustration**, not historical documentation or permission to use protected branding commercially.

## Shared architecture (proposed only)

```text
Project UI / Ask AI
       ↓
Shared client adapter (future shared/ai/)
       ↓
Private local or server-side API gateway
       ↓
Selected AI provider
       ↓
Labeled suggestions → editable preview → user approval
```

- Preserve a **provider-agnostic interface** so the user may change AI services.
- **Do not place API keys in HTML, client-side JavaScript, public GitHub files, or URLs.** Use a private gateway with credentials in environment variables or a secret manager.
- Default to **no AI requests**, no telemetry, and no API charges until the user explicitly invokes assistance.
- Where practical, provide cost/usage visibility and controls. An API subscription/billing account is separate from a ChatGPT subscription.
- Treat uploaded artwork and prompts as potentially private. Disclose when content will be transmitted to an external provider and offer a cancel option.
- Keep ordinary SVG/Canvas/WebGL tools useful **without AI or network access**.
- Validate structured output before applying it; never allow AI-generated commands or markup to bypass normal application checks.

## Creative integrity

- Clearly label real-world facts, plausible-but-unverified details, and intentional fiction.
- Research genuine historical details when factual authenticity matters; don't use model confidence as a substitute for a source.
- Prefer original band names, designs, fonts and fictional brands to close copies of recognizable logos or protected identities.
- Distinguish **actual vector geometry** from raster effects or WebGL-rendered pixels, including in exports.
- Keep AI proposals reversible and user-approved.

## Scope and next steps

This document records a shared **design direction**, not a mandate to integrate an API immediately.

Possible first implementation, later: a minimal user-initiated text prompt in one experiment, the 0–100 creative control, a provider adapter behind a private gateway, labeled suggestions, and an explicit apply/undo step. Only extract a reusable module after it proves useful.

**Decision status:** Proposed, not scheduled. No API provider or backend is chosen.

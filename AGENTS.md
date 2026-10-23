# Codex Instructions — Art Engine Lab

## Mission

This is a creative **experimental monorepo** of related but independent art-tech projects. Read `README.md`, `docs/VISION.md`, and `docs/DECISIONS.md` before making substantial architectural changes.

## Rules

1. **Scope work to the requested subproject.** Do not modify other subprojects without explicit authorization. Shared files may be changed only with an explanation of which projects are affected.
2. **Distinguish decisions from brainstorming.** The contents of `docs/IDEAS.md` are possibilities, not requirements; do not implement them all by default.
3. **Favor small, inspectable changes.** Explain choices and trade-offs in plain language; preserve working prototypes rather than rewriting unrelated modules.
4. **Preserve reference assets.** Never overwrite originals. Use derived filenames/folders for output. Avoid committing private/unlicensed assets without permission.
5. **Be precise about vectors.** SVG paths/shapes may be scalable; Canvas/WebGL rendered pixels and embedded raster textures are not inherently vector. Do not claim mixed artwork is fully vector.
6. **Protect repeat correctness.** Clearly distinguish phase shifts (which can preserve periodicity), geometry changes, motif relocation, and intentional misregistration (which may introduce seams). Test edge/corner behavior for claimed seamless results.
7. **Keep artist control.** Prefer reversible, understandable controls and visible previews; AI suggestions should remain editable.
8. **Document tests and uncertainty.** Identify assumptions, unsupported file types, export limitations, and any subjective visual assessments.
9. **No external services by default.** Ask before adding paid APIs, cloud dependencies, credentials, telemetry, or publishing assets.
10. **Do not commit secrets or large derived binaries** without a clear reason. Keep environment-specific configuration out of version control.

## Workflow

- Start by stating the specific subproject and intended files.
- Make a concise plan for anything nontrivial.
- Implement and test within scope.
- Summarize changes, how to run them, relevant validation, limitations, and possible next experiments.
- Update `docs/DECISIONS.md` only when a genuine design decision has been made, not for every idea.

Subprojects may add narrower `AGENTS.md` instructions once their needs become clear.

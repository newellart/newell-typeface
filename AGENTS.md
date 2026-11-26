# Newell Typeface — Agent Guide

Open-license (OFL) geometric display typeface. `SPEC.md` is the constitution — every glyph, kerning pair, and weight answers to it. Read it before touching outlines.

## Design law (from SPEC.md)

- Three primitives only: **Rail** (vertical/horizontal bar), **Diagonal** (45° stroke), **Junction** (squared union). Constant stroke width.
- No curves, no rounding. Every terminal squared; every corner is 90° or 45°.
- Signature gesture: the **N diagonal** inherited from the wordmark.

## Build

- Sources are UFO: `sources/Newell-Regular.ufo` (+ weights as added).
- Python pipeline in `scripts/`: `build.py` (single), `build_all.py` (all masters), `preview.py` / `_preview/` for proofing, `render_assets.py` + `render_favicons.py` for derived graphics, `screenshot.py` for specimen captures.
- CI in `.github/workflows/` (`ci.yml` builds on push; `release.yml` ships). Anything that breaks the build never reaches `master`.

## Rules

- `SPEC.md` changes require a ROADMAP.md note — the spec and roadmap move together.
- OFL.txt and AUTHORS.txt must stay in sync with any redistribution.
- Proof every glyph change with `scripts/preview.py` before committing; screenshots via `scripts/screenshot.py` for review artifacts.

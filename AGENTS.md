# AGENTS.md

Repo-level working preferences for `~/Dev/oleamediaco`.

## Response Protocol

- If a task may take more than a few seconds, send a short acknowledgment before doing the work.
- Read and follow this file before making changes.
- For changes intended to be viewed externally, commit and push once complete unless the user asks not to.

## Defaults

- Prefer `rg` and `rg --files` for search.
- Prefer small, direct edits over broad refactors.
- Prefer Python for one-off scripts and automation tasks.
- If Python dependencies are introduced, prefer `uv` for environment and package management.

## Repo Workflow

- Run commands from the repo root: `~/Dev/oleamediaco`.
- Make small, clear commits with the prefix `oleamediaco:`.
- Default to keeping `main` pushable.
- Use branches for larger changes; preferred branch prefix: `codex/`.
- After modifying the site, update docs when needed.

## Versioning

- Use visible app versions in the form `vX.Y`.
- `X` is the number of days since `2026-02-28`.
- `Y` increments with each build/change on that same day.
- Always bump `Y` for each new build on the same day.
- Update the version badge in any topbar or footer that shows the version.
- Also bump CSS/JS cache-bust query strings (`?v=X.Y`) in every HTML file.

## Workspace Structure

- Repo root: `~/Dev/oleamediaco`
- Variant launcher: `index.html`
- Design variants: `v1/`, `v2/`, `v3/`
- Shared scripts: `theme-toggle.js`, `before-after-slider.js`, `shared-translations.js`, `shared-i18n.js`
- Shared styles: `variants-base.css`
- Assets: `assets/` (logos, before/after images)
- PDFs: `OleaMediaCo-Offer-EN.pdf`, `OleaMediaCo-Oferta-ES.pdf`, `OleaMediaCo-Offre-FR.pdf`
- Source materials: `source/`

## Local Preview

- Start a local server from the repo root: `python3 -m http.server 8000`
- Variant launcher: `http://localhost:8000/`
- Example variant: `http://localhost:8000/v1/`

## PDF Source Workflow

Source files live under `source/`. If PDF content changes, regenerate from `source/` and keep output PDFs in the repo root so links stay valid.

## Execution Discipline

- Prefer deterministic tooling over manual repetition.
- Before adding new scripts, check whether the repo already contains a file or workflow that solves the task.
- If a task fails, read the full error, fix the cause, and retest.
- Keep secrets out of source files.

## Python Hygiene

- Do not commit virtual environments such as `.venv/`.
- Do not commit Python cache artifacts such as `__pycache__/` or `*.pyc`.

## Safety

- Do not delete or overwrite user files without explicit confirmation.
- Do not rewrite Git history unless explicitly requested.

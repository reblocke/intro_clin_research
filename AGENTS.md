# AGENTS

## Project Purpose
Guide for students residents and fellows doing clinical research

## Public and Data-Safety Rules
- Treat this repository as public. Do not add PHI, restricted datasets, credentials, private drafts, or publisher-formatted article text.
- Teaching materials only
- Manuscript status: No manuscript version expected

## How to Orient Quickly
- Start with `README.md` for project scope, workflow, data notes, citation, and license information.
- Use `CITATION.cff` for structured citation metadata when present.
- Inspect scripts/notebooks before running them; do not assume generated outputs are current.

## Workflow
The Quarto book is configured by `_quarto.yml` and starts at `index.qmd`; rendered output goes to `docs/`. Use `quarto render` for book configuration/navigation changes, or render the affected `.qmd` chapter for local content/layout verification after checking its executable chunks and dependencies. Documentation-only instruction edits need reference and whitespace checks.

## Verification Before Publishing Changes
- Run `git diff --check`.
- Validate `CITATION.cff` as YAML after citation edits.
- Do not commit generated outputs, logs, caches, virtual environments, `.DS_Store`, or checkpoint files unless intentionally released.
- For clinical or collaborator data, confirm that no row-level restricted data or identifiers are included.

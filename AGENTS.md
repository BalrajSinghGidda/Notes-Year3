# Vault rules — GNDEC notes

Permanent rules for all vault work. Read before any bulk edit or reformat.

## Never reformat without explicit permission

- `Archive/` — archived source dumps. Never reformatted, reorganized, or edited. Read-only.
- `Templates/` — existing templates are never reformatted. New templates may be added freely.
- Tooling folders (`copilot/`, `.copilot/`, `.opencode/`, `.agents/`, `.claude/`, `.obsidian/`) — never touched.

## Vault map

- `Home.md` — text index of all notes.
- `Mind Map.canvas` — visual index; must stay valid JSON Canvas 1.0.
- `ML/` — 9 topic notes (one md per topic, template structure).
- `DAA/` — 4 notes: Travelling Salesman Problem, Branch and Bound, Bellman Ford, Multi-graph.
- `Reference/` — LaTeX Math Symbols cheat sheet.
- `Templates/Lecture Note.md` — canonical layout for lecture/topic notes.

## Topic-note format

- Frontmatter: `subject` (ML | DAA), `date`, `topics-covered`.
- Sections in order: `## Topics covered` → `## Notes` → `## Examples worked in class` → `## Questions to research` → `## See also`.
- Bullets `- ` with 4-space nesting; math in `$...$`; wikilinks `[[Title]]`; no emojis.

## Data preservation

- `DAA/Travelling Salesman Problem.md` contains two inline SVG diagrams that cannot be re-typed — never rewrite the file wholesale; edit around the SVG blocks (or use a script that passes them through byte-for-byte).
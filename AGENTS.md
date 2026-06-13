# Agent Guide — Just Artifacts

## Project Overview

A single-page web application for previewing AI-generated code artifacts.
Vanilla JS + Terminal Brutalist CSS design system. No build step. Everything persists in
`localStorage`.

```
/
├── index.html          # The entire application (single page)
├── README.md           # Project documentation
├── AGENTS.md           # This file — conventions for agents
├── .gitignore          # Git ignore rules
├── assets/             # Static assets (favicon, screenshots, images)
│   ├── favicon.svg
│   └── screenshot.png
├── temp/               # Scratch workspace (gitignored)
```

## Temp Directory (`/temp/`)

`temp/` is a **scratch workspace** — NOT a deliverable. It lives at the repo
root for convenience but is excluded from version control via `.gitignore`.

### Rules

- Temporary/exploratory outputs go here: prototypes, design explorations,
  spec drafts, one-off HTML presentations, data exports for analysis.
- **Never** commit anything inside `temp/`. It is gitignored.
- Keep it tidy. Clean up files that are no longer relevant.
- If a file in `temp/` becomes permanent project code, move it to the
  appropriate location in the repo root and delete the temp copy.

### Example uses

- `temp/catalog-prototype.html` — exploratory UI for a new feature
- `temp/api-response.json` — saved API output for debugging
- `temp/design-variant-compare.html` — side-by-side visual comparison

## Conventions for Agents

1. **Surgical edits.** Change only what the task requires. Don't reformat
   adjacent code or "improve" things outside the scope.
2. **Design system.** This project uses the Terminal Brutalist custom CSS design
   system (see `<style>` block in `index.html`). Use the CSS variables
   (`--bg`, `--fg`, `--border`, `--border-dim`, `--muted`, `--danger`,
   `--pane-bg`, `--mono`, `--sans`) and existing class patterns
   (`.btn`, `.pane`, `.pane-header`, `.sidebar-item`, `.empty-state`).
   Do not introduce Tailwind or other CSS frameworks.
3. **No speculative features.** Build what was asked, nothing more.
4. **Temp files belong in `temp/`.** If you need to generate an exploratory
   output, put it in `temp/`. Do not use `/tmp` or other external paths.

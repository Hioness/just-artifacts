# Agent Guide — Just Artifacts

## Project Overview

A single-page web application for viewing and comparing AI-generated HTML artifacts.
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

## Architecture

The app is a **dual-pane viewer** (not a code editor). Two preview panes (A and B)
display HTML artifacts loaded via drag & drop or click-to-browse.

### State Model

```js
state = {
  artifacts: [],        // Saved artifacts (persisted in localStorage)
  viewMode: 'single',   // 'single' | 'split'
  activePane: 0,        // 0 = Pane A, 1 = Pane B
  panes: [
    { artifactId, title, code },  // Pane A
    { artifactId, title, code }   // Pane B
  ]
}
```

- Each pane holds its own document independently.
- `artifactId` links a pane to a saved artifact (null = unsaved copy).
- localStorage key: `just-artifacts-v2-data`

### Key Patterns

- **Pane focus**: Click a pane header to focus it. The header title input and Save
  button always operate on the active pane.
- **File loading**: Drag & drop onto panes, or click empty pane to open file picker.
  Dropping two files auto-populates both panes and switches to split view.
- **Rendering**: Panes only re-blob when code actually changes (avoids iframe flash).
  Empty panes use `about:blank` to prevent accidental parent page reloads.

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
   (`.btn`, `.btn-group`, `.preview-pane`, `.pane-header`, `.pane-tag`,
   `.sidebar-item`, `.empty-state`, `.drop-overlay`).
   Do not introduce Tailwind or other CSS frameworks.
3. **No speculative features.** Build what was asked, nothing more.
4. **Temp files belong in `temp/`.** If you need to generate an exploratory
   output, put it in `temp/`. Do not use `/tmp` or other external paths.

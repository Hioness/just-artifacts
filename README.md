# Just Artifacts

A single-page web application for viewing and comparing AI-generated HTML artifacts. This is a personal tool—no backend, no authentication, no sharing. Everything persists in `localStorage`.

## Features

- **Dual-Pane Viewer**: Two preview panes (A and B) for side-by-side comparison of HTML artifacts.
- **Drag & Drop**: Drop `.html` files directly onto either pane to load them. Drop two files to auto-populate both panes in split view.
- **Click to Browse**: Click an empty pane to open a file picker.
- **Single / Split View**: Toggle between focusing on one pane or viewing both side-by-side.
- **Device Presets**: Test responsiveness with Mobile (375px), Tablet (768px), Desktop (1024px), and Full Width viewport presets.
- **Fullscreen Mode**: View the active pane's artifact in a distraction-free fullscreen overlay.
- **Local Persistence**: Save, load, and delete artifacts using browser `localStorage`. Pane state and view mode persist across sessions.
- **Keyboard Shortcuts**: `Ctrl+S` save, `Ctrl+N` clear active pane, `Ctrl+B` toggle sidebar.

## Design System — Terminal Brutalist

The interface follows a strict design language:

- **Monospace everywhere.** All UI chrome—headers, buttons, labels, inputs—uses a monospace font stack. Sans-serif is reserved for body prose only.
- **No border-radius.** Every element is a sharp rectangle. Hard edges read as infrastructure.
- **Offset shadows, not blurred.** Buttons use flat offset shadows (`2px 2px 0`) and invert colors on hover. No gradients, no blur.
- **Uppercase labels.** All UI chrome text is uppercase. Visual discipline for a tool aesthetic.
- **Semantic color only.** The palette is near-monochrome (`#1a1a1a` background, `#ffffff` foreground). Color enters only through semantic states: green for additions, red for danger.
- **1px borders.** Every line is 1px solid. No thicker lines, no light/dark gradient tricks.

## Usage

**Live site**: [just-artifacts.vercel.app](https://just-artifacts.vercel.app/)

Simply open `index.html` in your web browser. No build step or server required.

1. **Load Artifacts**: Drag & drop HTML files onto the preview panes, or click an empty pane to browse.
2. **Compare**: Use the Single/Split toggle to view one or both panes.
3. **Save**: Click "Save" to store the active pane's artifact locally. You must rename it from "New_Artifact".
4. **Manage**: Open the sidebar (`Ctrl+B`) to view, load, and delete saved artifacts.

## Tech Stack

- **HTML5**
- **Vanilla JavaScript**
- **Terminal Brutalist CSS** (custom design system, no frameworks)

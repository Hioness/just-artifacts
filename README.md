# Just Artifacts

A single-page web application for previewing AI-generated code artifacts. This is a personal tool—no backend, no authentication, no sharing. Everything persists in `localStorage`.

## Features

- **Code Preview**: Live preview of HTML/CSS/JS or React code.
- **Language Support**: Toggle between standard HTML and React (with Babel/React 18).
- **Device Presets**: Test responsiveness with Mobile, Tablet, Desktop, and Custom width presets.
- **Fullscreen Mode**: View artifacts in a distraction-free modal.
- **Local Persistence**: Save, load, and delete artifacts using browser `localStorage`.
- **Zero Dependencies**: Built with Vanilla JS and Tailwind CSS via CDN.

## Usage

Simply open `index.html` in your web browser. No build step or server required.

1. **Paste Code**: Paste your HTML or React code into the left panel.
2. **Select Language**: Choose "HTML" or "React" from the footer.
3. **Preview**: See the result in the right panel.
4. **Save**: Click "Save" to store the artifact locally. You must rename it from "New_Artifact".
5. **Manage**: Open the sidebar (bottom-left) to view and load saved artifacts.

## Tech Stack

- **HTML5**
- **Tailwind CSS** (CDN)
- **Vanilla JavaScript**
- **React/ReactDOM/Babel** (CDN for React preview mode)

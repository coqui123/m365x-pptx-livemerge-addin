# m365x-pptx-livemerge-addin

Static files for a personal Office add-in (PowerPoint, task pane) served by GitHub Pages.

- `taskpane.html`: loads Office.js from Microsoft's CDN, waits for `Office.onReady`, and sets a small ready marker. It has no buttons, makes no network calls of its own, and stores nothing.
- `manifest.xml`: add-in-only XML manifest pointing at `https://coqui123.github.io/m365x-pptx-livemerge-addin/taskpane.html`.
- `assets/`: icons.

All document logic runs in a separate local tool, which checks the sha256 of `taskpane.html` before using the pane. This repository contains no data, credentials, or configuration. Changing `taskpane.html` changes its hash, so the local tool will refuse it until the pinned value is updated.

License: MIT.

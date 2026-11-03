# c4cyber: student schedule site

- Static GitHub Pages site: `index.html` (page) reads `schedule.json` (all content). Edit content in `schedule.json`.
- On every change, raise `"version"` in `schedule.json` by 0.1 (1.0 → 1.1 → 1.2) and set `"updated"` to today's date (YYYY-MM-DD). The version shows as a small note at the top of the page.
- Do not push to GitHub until the user confirms. Make changes locally, show them in the preview, and push only after the user says to.

# 🎓 Learning Path Tracker

Interactive GitHub Pages app for tracking LinkedIn Learning course completion with certificate proof.

## Features

- **Progress tracking** – Check off completed courses with automatic date stamps
- **Certificate proof** – Paste LinkedIn certificate URLs as verifiable evidence
- **Cross-device sync** – Progress stored on GitHub, accessible from any device
- **Owner / Viewer mode** – Owner (with token) edits; colleagues view read-only
- **Bilingual** – Automatic DE/EN based on browser language, manually switchable
- **Dynamic courses** – Courses loaded from JSON; upload a new file each year

## Live Page

- **Viewer (read-only):** [andymization.github.io/learning-path](https://andymization.github.io/learning-path/)
- **Owner (read+write):** Same URL with `#token=<GITHUB_PAT>` in the hash

## How It Works

1. `index.html` loads courses from `courses-YYYY.json` (current year first)
2. Progress is stored in `state.json` (read publicly via raw URL, written via GitHub API)
3. Owner authenticates via a fine-grained GitHub PAT embedded in the URL hash
4. Certificate links are stored per course and visible to all viewers

## Adding Courses for a New Year

1. Create `courses-2027.json` (same structure as `courses-2026.json`)
2. Upload to this repo
3. The page auto-detects the newest courses file

## File Structure

| File | Purpose |
|------|---------|
| `index.html` | Main app (HTML + CSS + JS, no dependencies) |
| `courses-2026.json` | Course definitions (blocks, titles, URLs, durations) |
| `state.json` | Progress state (completion dates, certificate URLs) |
| `README.md` | This file |

## Source

Courses selected from the approved **LinkedIn Course List 2026** (Excel).
Each course includes its Excel row number for traceability.
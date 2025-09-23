# Repository Guidelines

## Project Structure & Module Organization
- Standalone HTML apps sit at the repo root; `munjjak_with_odt(ver.1.0).html` is the primary interface, with `odt_to_hwp(SahAI).html` and `poe.html` covering focused flows.
- Reference briefs for external agents live in `CLAUDE.md` and `GEMINI.md`; update these alongside feature changes.
- Sample fixtures (ODT, PDF, XLSX) reside in `문짝/`; keep new test documents there so they remain out of versioned HTML.
- Legacy builds stay in `bak/`; clone before experimenting so prior baselines remain untouched.

## Build, Test, and Development Commands
- No build step is required—double-click any HTML file or run `start munjjak_with_odt(ver.1.0).html` on Windows to launch locally.
- For consistent browser testing, serve the root with `python -m http.server 8000` and open `http://localhost:8000/`.
- Clear caches between iterations (Ctrl+Shift+R) to reload embedded scripts.

## Coding Style & Naming Conventions
- Use 4-space indentation throughout HTML, CSS, and inline JavaScript blocks; keep CSS and JS co-located unless a refactor removes duplication.
- Prefer camelCase for JavaScript functions (`processPdfBatch`) and descriptive kebab-case for CSS classes (`workflow-container`).
- When expanding features, document UI copy in Korean first, with English comments only when vital for maintenance.
- Reuse existing utility helpers before introducing new globals; keep error messages user-facing and polite.

## Testing Guidelines
- Validate merge/split flows in Chrome and Edge using the fixtures in `문짝/`; cover PDFs, multi-sheet XLSX, and ODT samples each pass.
- Confirm downloads preserve original filenames plus suffixes like `_merged` or `_split-page-1` to avoid clobbering.
- Capture console output—treat any uncaught exception as a blocker before sharing builds.

## Commit & Pull Request Guidelines
- The current log shows terse commits such as `s`; replace this with `scope: imperative summary` (e.g., `ui: refine drop-zone copy`) to aid traceability.
- Each PR should describe the user workflow affected, list manual test cases run, and attach before/after screenshots when UI shifts.
- Link Trello or issue tracker IDs in the description so downstream reviewers can audit requirements quickly.

## Security & Data Handling
- Keep all processing client-side; never add calls that move files off-device or introduce remote analytics.
- Audit third-party CDN upgrades for license changes before merging.

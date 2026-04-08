# Changelog

All notable changes to PDF Toolkit are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [1.0.0] — 2025

### Added
- ✂️ Extract specific pages or ranges from a PDF
- 🔗 Merge multiple PDFs into one
- 📄 PDF → DOC text extraction
- 📝 DOCX → PDF conversion using mammoth.js
- 🖼️ Image (PNG/JPG) → PDF conversion
- 📋 Extract specific pages from a DOCX as PDF
- Custom output filename support
- Loaded files list displayed after upload
- Post-action "Clear & upload new" and "Reload page" buttons
- Library load status banner on startup

### Security
- MIME type whitelist validation on all uploads
- Magic byte (`%PDF`) verification before processing
- Empty file (0-byte) rejection
- 50 MB per-file size limit
- Filename sanitization (XSS, path traversal, null bytes)
- Hardened page range parser (no negatives, floats, scripts, DoS)
- Page range capped at 500 per operation
- Object URLs revoked 6 seconds after download
- Buttons locked during async operations (no race conditions)
- All filenames rendered via `textContent` (no XSS via `innerHTML`)
- No `alert()` — inline styled messages only
- Errors logged to `console.error`, not exposed to users
- Google Fonts removed (no external IP leak)
- No `localStorage`, `sessionStorage`, or cookies
- No `fetch()` or network requests with file data

### Fixed
- Replaced broken fabricated SRI hashes (were wrong length, silently blocked all scripts)
- Removed top-level `PDFLib` destructuring (crashed entire script if library failed to load)
- Removed pdf.js dependency (web worker requirement caused silent failures)
- Fixed file list not showing after upload (`display:''` → `display:'block'`)
- Replaced `f.text()` on DOCX binary with mammoth.js proper parser
- Replaced `unpkg.com` with `cdnjs.cloudflare.com` for pdf-lib

---

## How to read version numbers

`MAJOR.MINOR.PATCH`

- **MAJOR** — breaking changes or full rewrites
- **MINOR** — new features, backward compatible
- **PATCH** — bug fixes and security patches

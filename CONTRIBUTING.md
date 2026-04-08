# Contributing to Advanced-PDF-Document-Utility-Offline-Edition

Thank you for your interest in contributing! This is a simple single-file project — contributions of all sizes are welcome.

---

## Getting started

```bash
# 1. Fork the repo on GitHub, then clone your fork
git clone https://github.com/rajathchannasetty-sys/Advanced-PDF-Document-Utility-Offline-Edition.git
cd pdf-toolkit

# 2. Open the app locally
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux

# Or serve it with Python for a more realistic environment
python3 -m http.server 8080
# Visit http://localhost:8080
```

---

## Project structure

Everything lives in **one file**: `index.html`

Inside that file:
- **CSS** — between `<style>` tags (lines ~20–160)
- **HTML** — the visible UI (lines ~160–250)
- **JavaScript** — between `<script>` tags at the bottom

---

## What to work on

Check the [Issues](../../issues) tab for open bugs and feature requests. 
Good first issues are labelled `good first issue`.

Popular areas for contribution:
- Better PDF text extraction
- Drag to reorder merge files
- Dark/light mode toggle
- Progress bar for large files
- Password-protected PDF support

---

## Guidelines

### Core rule — keep it local
This tool's main value is that **nothing is uploaded**. Any contribution that sends file data to a server will not be merged.

### Keep it a single file
No build tools, no bundlers, no `npm install`. The goal is that anyone can download `index.html` and it just works. External libraries are loaded from CDN only.

### Code style
- Use `var` or `const`/`let` consistently with surrounding code
- Wrap async operations in `try/catch/finally`
- Always `lock()` and `unlock()` buttons around async operations
- Use `textContent` not `innerHTML` for user-controlled data
- Always call `URL.revokeObjectURL()` after downloads

### Security checklist for new features
Before submitting, verify your code:
- [ ] Validates file MIME type before processing
- [ ] Checks magic bytes for PDFs
- [ ] Sanitizes any user-provided filenames
- [ ] Wraps async code in try/catch/finally
- [ ] Disables buttons during processing
- [ ] Revokes Object URLs after download
- [ ] Does not use `innerHTML` with user data
- [ ] Does not send data to external servers

---

## Submitting a Pull Request

1. Create a branch: `git checkout -b fix/my-fix` or `feature/my-feature`
2. Make your changes in `index.html`
3. Test in at least two browsers (Chrome + Firefox recommended)
4. Update `CHANGELOG.md` under a new version or under `Unreleased`
5. Push: `git push origin your-branch-name`
6. Open a Pull Request with a clear description of what changed and why

---

## Reporting bugs

Use the [Bug Report template](../../issues/new?template=bug_report.md). Include browser, OS, and any console errors (F12 → Console tab).

## Reporting security issues

**Do not open public issues for security vulnerabilities.** See [SECURITY.md](SECURITY.md).

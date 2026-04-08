# PDF Toolkit 🗂️

> A fully offline, browser-based PDF & document utility. No uploads. No server. No data leaves your machine.

**🔗 Live Demo:** `https://YOUR-USERNAME.github.io/pdf-toolkit/`

---

## ✨ Features

| Feature | Description |
|---|---|
| ✂️ **Extract PDF Pages** | Pick specific pages or ranges (e.g. `1, 3-5, 8`) from any PDF |
| 🔗 **Merge PDFs** | Combine multiple PDFs into one file in your chosen order |
| 📄 **PDF → DOC** | Extract text content from a PDF into a Word-compatible document |
| 📝 **DOCX → PDF** | Convert a DOCX file's text into a clean, paginated PDF |
| 🖼️ **Image → PDF** | Combine PNG/JPG images into a single PDF document |
| 📋 **Extract DOCX Pages** | Pull specific pages from a DOCX and export as PDF |

---

## 🔒 Privacy & Security

- **100% local processing** — your files never leave your browser
- **No server, no backend, no database**
- **No file uploads** to any external service
- MIME type validation on every file
- Magic byte (`%PDF`) verification before processing
- Filename sanitization (strips XSS, path traversal, special chars)
- Page range input hardened against injection and DoS attacks
- Object URLs revoked after download (no memory leaks)
- Buttons locked during operations (no race conditions)

---

## 🚀 How to Use

1. Open the [live site](https://github.com/rajathchannasetty-sys/Advanced-PDF-Document-Utility-Offline-Edition) in any modern browser
2. Drag & drop your files or click **Browse**
3. Choose an operation from the cards
4. Download your result — done!

**Supported file types:** PDF · DOCX · PNG · JPG (max 50 MB each)

---

## 🛠️ Tech Stack

| Library | Version | Purpose |
|---|---|---|
| [pdf-lib](https://pdf-lib.js.org/) | 1.17.1 | PDF creation, manipulation, merging, page extraction |
| [mammoth.js](https://github.com/mwilliamson/mammoth.js) | 1.6.0 | DOCX text extraction |

No build tools. No frameworks. No npm. Pure HTML + CSS + JavaScript.

---

## 📁 Project Structure

```
pdf-toolkit/
├── index.html          # The entire app (single file)
├── README.md           # This file
├── LICENSE             # MIT License
├── SECURITY.md         # Security policy
├── CHANGELOG.md        # Version history
└── .github/
    └── ISSUE_TEMPLATE/
        ├── bug_report.md
        └── feature_request.md
```

---

## 🖥️ Run Locally

No installation required. Just open `index.html` in your browser:

```bash
# Clone the repo
git clone https://github.com/YOUR-USERNAME/pdf-toolkit.git

# Open in browser (macOS)
open pdf-toolkit/index.html

# Open in browser (Windows)
start pdf-toolkit/index.html

# Open in browser (Linux)
xdg-open pdf-toolkit/index.html
```

Or serve it locally with Python (for development):

```bash
cd pdf-toolkit
python3 -m http.server 8080
# Then open http://localhost:8080
```

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m "Add: my feature"`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

Please read [SECURITY.md](SECURITY.md) before reporting vulnerabilities.

---

## 📋 Known Limitations

- PDF → DOC text extraction is best-effort. Scanned PDFs (image-based) may return no text.
- DOCX → PDF uses plain text rendering — formatting, fonts, and images are not preserved.
- Page extraction from DOCX splits by ~3000 characters per page, not by document-defined page breaks.
- Files above 50 MB are rejected to protect browser performance.

---

## 📄 License

[MIT](LICENSE) © Rajath Channasetty

---

## 👤 Author

**Rajath Channasetty**
- LinkedIn: [@rajath-channasetty](https://linkedin.com/in/rajath-channasetty)
- GitHub: [@YOUR-USERNAME](https://github.com/rajathchannasetty-sys)

---

<p align="center">Made with ❤️ — 100% private, 100% free</p>

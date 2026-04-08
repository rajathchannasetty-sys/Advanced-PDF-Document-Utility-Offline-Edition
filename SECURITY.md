# Security Policy

## Supported Versions

| Version | Supported |
|---|---|
| Latest (main branch) | ✅ |
| Older commits | ❌ |

## Security Design

PDF Toolkit is a **fully client-side application**. All file processing happens in the user's browser using JavaScript. No files, metadata, or personal data are ever transmitted to any server.

### Protections in place

| Area | Protection |
|---|---|
| File validation | MIME type whitelist + magic byte (`%PDF`) verification |
| File size | Hard 50 MB limit per file |
| Page input | Strict regex parser — rejects floats, negatives, scripts, SQL |
| Page range DoS | Capped at 500 pages per range |
| Filename | Strips `<>:"\/\|?*`, path traversal (`../`), null bytes |
| Memory | Object URLs revoked 6 seconds after download |
| Race conditions | Buttons disabled during async operations |
| XSS | All user data rendered via `textContent`, never `innerHTML` |
| CDN | Libraries loaded via HTTPS from cdnjs / jsdelivr |
| Data storage | No `localStorage`, `sessionStorage`, or cookies used |
| Network | No `fetch()` or `XHR` calls with file data |

## Reporting a Vulnerability

If you discover a security vulnerability, please **do not open a public GitHub issue**.

Instead, report it privately:

1. Go to the **Security** tab of this repository
2. Click **"Report a vulnerability"**
3. Fill in the details

Or email directly: `your-email@example.com`

**Please include:**
- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

You can expect a response within **48 hours**. If the vulnerability is confirmed, a fix will be released as soon as possible and you will be credited in the changelog.

## Third-Party Libraries

| Library | Source | Version |
|---|---|---|
| pdf-lib | cdnjs.cloudflare.com | 1.17.1 |
| mammoth.js | cdn.jsdelivr.net | 1.6.0 |

Both are loaded over HTTPS. Monitor their respective repositories for security advisories:
- https://github.com/Hopding/pdf-lib
- https://github.com/mwilliamson/mammoth.js

---
paths:
  - "**/*.html"
  - "**/*.js"
  - "assets/**"
---
This is a static, client-only site — everything here ships to the browser and is public:

- **NEVER embed secrets, API keys, tokens or credentials** in HTML or client-side JS. Anything committed here is public.
- Only **publishable/public keys** (e.g. a domain-restricted analytics or maps key) may appear in the frontend.
- No unsanitized `innerHTML` / inline handlers built from user- or URL-derived data (XSS).
- Keep `robots.txt` / `sitemap.xml` consistent when adding or renaming pages.

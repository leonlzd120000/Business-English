# Workflows

## EL

Trigger: the user sends `EL` plus a URL, or asks FE to turn a news link into a Business English learning page.

Process:

1. Firecrawl scrapes the URL and returns the article text, title, source URL, publication date if available, and short source notes.
2. FE creates a new static HTML learning page in `/Users/lee/Documents/EL/LE`.
3. The page includes the English article, Chinese translation, core vocabulary, Chinese definitions, example sentences, and audio controls.
4. Generate Edge TTS MP3 files for core vocabulary under `audio/<article-slug>/`.
5. Update `index.html` with a visible link to the new page while preserving all existing pages.
6. Commit and push to `git@github.com:leonlzd120000/Business-English.git`.
7. GitHub Actions publishes GitHub Pages.

Rules:

- Do not delete or overwrite existing generated pages.
- Keep mobile responsive layout as a default requirement.
- Preserve the existing Economist-style visual language unless the user asks for a new direction.
- Final reply must include the article page URL, commit id, and deployment status.

# Minimal Image Compare Slider for Notion

A lightweight, transparent-background before/after slider for embedding in Notion via GitHub Pages. The page has no framework or external dependencies.

## Publish with GitHub Pages
1. Create a GitHub repository.
2. Upload `index.html` to the repository root.
3. In **Settings → Pages**, deploy from the `main` branch and `/ (root)`.
4. Wait for GitHub Pages to publish the site. Open the HTTPS URL.
5. Add `?configure=1` to the URL to open the settings panel.
6. Enter two image HTTPS URLs, optional prompt text, and choose which labels/prompts to show.
7. Click **取得嵌入連結**, then paste that URL into a Notion `/embed` block.

## Notes
- The page has a transparent background and minimal styling, so it blends into Notion.
- Images need direct HTTPS URLs that can be loaded by viewers. This tool does not upload images.
- Prompt text and display options are encoded in the generated URL. Do not put confidential text in the URL.
- With GitHub Pages, the page itself is public. Use only images and prompts approved for public access.

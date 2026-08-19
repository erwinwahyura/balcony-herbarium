# balcony-herbarium

Personal plant care catalog styled like herbarium specimen tags.

A single-page static site (`index.html`) presenting a balcony plant collection as numbered herbarium specimen sheets — photo, Latin/common/local name, light & water care, and notes — in Indonesian. Design is quiet and editorial (Fraunces serif + Work Sans + IBM Plex Mono, generous whitespace, hairline rules, seal-style specimen numbers) so it stays legible as the collection grows.

## Specimens

| No. | Latin name | Common name | Nama lokal |
|-----|-----------|--------------|------------|
| 01 | *Tradescantia zebrina* | Wandering Jew | Adam Hawa Rambat |
| 02 | *Asparagus setaceus* | Asparagus Fern | Pakis Asparagus |
| 03 | *Philodendron hederaceum* 'Brasil' | Philodendron Brasil | Filodendron Brasil |
| 04 | *Monstera adansonii* var. | Monstera Variegata | Janda Bolong Variegata |
| 05 | *Epipremnum aureum* 'Marble Queen' | Pothos Marble Queen | Sirih Gading Marmer |
| 06 | *Aglaonema* sp. | Chinese Evergreen | Sri Rejeki |

## Structure

- `index.html` — the catalog. Each specimen sheet is static markup (not JS-generated) so search engines and social crawlers see full content without running JavaScript. A small script only handles the location/media filter toggles, using `data-loc`/`data-media` attributes on each `.sheet` and index-nav link.
- `cara-merawat-*.html` — one dedicated care-guide page per specimen (e.g. `cara-merawat-asparagus-fern.html`), targeting long-tail searches like "cara merawat asparagus fern". Each has its own meta tags, canonical URL, and JSON-LD (`Article`, `HowTo`, `FAQPage`, `BreadcrumbList`).
- `assets/style.css` — shared stylesheet for every page.
- `assets/` — specimen photos (`01-tradescantia.jpg` … `06-aglaonema.jpg`)
- `robots.txt`, `sitemap.xml` — crawler entry points; sitemap lists the index and every care-guide page.

## Adding a specimen

1. Add a new `<article class="sheet" id="sXX" data-loc="…" data-media="…">` block to `index.html` (copy an existing one for the shape) and a matching `<a>` in `#indexNav`. Bump the footer count.
2. Drop its photo in `assets/`.
3. Create a `cara-merawat-<slug>.html` page (copy an existing one) with real care content, and link to it from the sheet's "Cara merawat …" line.
4. Add the new page to `sitemap.xml` and to the `ItemList` JSON-LD in `index.html`.

## SEO notes

- Content is server-renderable HTML, not injected via JS on load — this matters for crawlers (including ones that don't execute JavaScript) and for social-card previews.
- After deploying, submit `sitemap.xml` in Google Search Console and Bing Webmaster Tools so new/changed pages get crawled promptly.
- Keep page `<title>`/`<meta name="description">` and the `cara-merawat-*` filenames aligned with how people actually search (e.g. "cara merawat X", plant common/local names) — that phrasing match is what search engines match against queries.

## Usage

Open `index.html` directly in a browser, or serve the folder with any static file server.

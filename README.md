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

- `index.html` — styles + a `specimens` array (in an inline `<script>`) that's rendered into specimen sheets and the top index nav on load. No build step, no dependencies.
- `assets/` — specimen photos (`01-tradescantia.jpg` … `06-aglaonema.jpg`)

## Adding a specimen

Add a new object to the `specimens` array in `index.html` (see the existing six for the shape: `no`, `anchor`, `latin`, `common`, `local`, `accent`, `image`, `alt`, `locType`, `locLabel`, `trait`, `light`, `water`, `note`) and drop its photo in `assets/`. The card, index-nav entry, and footer count all update automatically — no markup duplication needed.

## Usage

Open `index.html` directly in a browser, or serve the folder with any static file server.

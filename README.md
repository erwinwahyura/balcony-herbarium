# balcony-herbarium

Personal plant care catalog styled like herbarium specimen tags.

A single-page static site (`index.html`) presenting a balcony plant collection as numbered specimen cards — photo, Latin & common name, light/water care, and care notes — in Indonesian.

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

- `index.html` — page markup, styles, and content (no build step, no dependencies)
- `assets/` — specimen photos (`01-tradescantia.jpg` … `06-aglaonema.jpg`)

> **Note:** `index.html` currently references photos as `images/0N-*.jpg`, but the files live in `assets/0N-*.jpg` directly (no `images` subfolder). Update the `src` paths or move the files to match before the photos will render.

## Usage

Open `index.html` directly in a browser, or serve the folder with any static file server.

# Herbář nálezů — Field Notebook for the "Česká flóra" Project

**A personal field-planning tool for chasing down the vascular plant species you're still missing from iNaturalist's Czech flora project.**

## Why this exists

[Česká flóra](https://www.inaturalist.org/projects/ceska-flora-projekt-ceske-botanicke-spolecnosti) is an iNaturalist project run by the Czech Botanical Society that tracks observations of vascular plants (Tracheophyta) across the Czech Republic, ranking contributors by how many distinct species they've documented. Climbing that leaderboard means one thing: finding species you haven't photographed yet.

The obvious problem is that "haven't photographed yet" is a list of over a thousand taxa, scattered across every corner of the country, each with its own flowering window, habitat preference, and — crucially — its own risk of being mistaken for a garden escapee rather than a genuinely wild plant. Figuring out *which* species to look for, *where*, and *when* by hand is not realistic.

This tool exists to answer one question quickly: **"I'll be in [place] around [time] — what am I missing that I could plausibly find there?"**

## What it does

- **Tracks your gap list.** Starts from the full species list of the project and your own observation history, and narrows it down to what you're actually still missing.
- **Filters by phenology.** Each species carries its flowering window (sourced from [Pladias](https://pladias.cz), the Czech flora database) and whether it's a tree/shrub identifiable year-round versus a herb you need to catch in bloom.
- **Shows real localities.** For every species, a set of geographically spread-out, real observation records (from [GBIF](https://www.gbif.org) and iNaturalist) are plotted on an interactive map — not just "somewhere in this county," but actual coordinates with dates and sources.
- **Flags cultivation risk.** A lot of "missing" species turn out to be garden ornamentals rather than wild plants (lilacs, ornamental cotoneasters, garden bulbs...). Each entry carries a "wild confidence" rating so you don't drive out to photograph someone's flowerbed.
- **Click-to-search on the map.** Set your search location by clicking or dragging a marker, adjust the radius, pick a month, and the tool filters and re-plots live.
- **Manage your own list.** Hide species temporarily from the map, or permanently remove ones you've since found — both persist between sessions.
- **Works offline as a single file.** No backend, no build step. It's one self-contained HTML file; open it in any browser.

## Data sources

- **[iNaturalist API](https://api.inaturalist.org)** — project membership, species counts, phenology (observation date distributions)
- **[Pladias](https://pladias.cz)** — flowering periods, growth form, native/non-native status, legal protection
- **[GBIF](https://www.gbif.org)** — geolocated occurrence records (aggregates iNaturalist plus herbarium and other datasets)

## A note on the data

Species entries are enriched in batches, cross-checked against the project's own source data, and corrected whenever a discrepancy turns up (wrong coordinates, mis-transcribed names, contaminated search results have all happened and been fixed along the way — see the in-code changelog comment near the top of the script for the running list of lessons learned). It's a living dataset, not a finished product: some species are still pending enrichment, and "wild confidence" ratings are a best-effort judgment call, not a guarantee.

## Running it

Open `herbar_nalezy.html` in a browser. That's it — no installation, no server. (Note: some features that require outbound network calls, such as map tile imagery, may not render inside embedded/sandboxed viewers; opening the file directly in a regular browser avoids this.)

---

*Built as a personal tool for one contributor's iNaturalist project — shared here in case the approach is useful to anyone else chasing the same kind of species list.*

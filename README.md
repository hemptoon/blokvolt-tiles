# blokvolt-tiles — data host for the blokvolt.com world map

Served by GitHub Pages at https://hemptoon.github.io/blokvolt-tiles/ (byte ranges for PMTiles, `Access-Control-Allow-Origin: *`).
Production data of the blokvolt.com world map since 11.11.2026 (REL1, "релиз мира"); R2 (`tiles.blokvolt.rs`) may replace
this host later by the owner's decision. Built by the evdb public layer (`run_public.sh`, K1) and the
pages bundle (`pages_json.py`, K3); see RUNBOOK "Dev previews" in hemptoon/blokvolt-rs.

- `world/<date>/world.pmtiles` — vector tiles, layer `sites`, z0–12.
- `data/<date>/` — cards, manifest, pages bundle and the ODbL dump that the preview workflow of blokvolt-rs downloads.
- `latest.json` — the current date, tiles and data folder (read by `scripts/dev_world_data.py` of blokvolt-rs at build time).
- `world/latest.json` → `world/manifest-<date>.json` → `world/cards-<date>/` — what the world map reads in the browser
  (`content/world/config.json` `data_base` = `https://hemptoon.github.io/blokvolt-tiles/world/`); the manifest names the tiles
  and the places relative to `world/`, the ODbL dump by absolute URL in `data/<date>/`.

History should not grow: a data update may replace the commits of `main` (force push). A weekly update writes `data/<date>/`,
`world/<date>/world.pmtiles`, extracts the cards into `world/cards-<date>/`, writes `world/manifest-<date>.json` and then both
`latest.json` files.

Data: © OpenStreetMap contributors (ODbL) · Open Charge Map (CC BY 4.0) · GeoNames (CC BY 4.0) and the official open
registries listed in `attribution.json`. The station layer as a database is available under the ODbL
(`data/<date>/odbl-<date>.csv.gz`, with its README).

# blokvolt-tiles — data host for the blokvolt.com world map

Served by GitHub Pages at https://hemptoon.github.io/blokvolt-tiles/ (byte ranges for PMTiles, `Access-Control-Allow-Origin: *`).
Production map data of blokvolt.com moved to R2 (`https://tiles.blokvolt.rs/world/`) with REL3 (11.11.2026); this host keeps
the pages bundles (`data/<date>/`, read by the hourly build of blokvolt.com), the dev previews and the fallback `world/`. Built by the evdb public layer (`run_public.sh`, K1) and the
pages bundle (`pages_json.py`, K3); see RUNBOOK "Dev previews" in hemptoon/blokvolt-rs.

- `world/<date>/world.pmtiles` — vector tiles, layer `sites`, z0–12.
- `data/<date>/` — cards, manifest, pages bundle and the ODbL dump that the preview workflow of blokvolt-rs downloads.
- `latest.json` — the current date, tiles and data folder (read by `scripts/dev_world_data.py` of blokvolt-rs at build time).
- `world/latest.json` → `world/manifest-<date>.json` → `world/cards-<date>/` — what the world map reads in the browser
  (`content/world/config.json` `data_base` = `https://hemptoon.github.io/blokvolt-tiles/world/`); the manifest names the tiles
  and the places relative to `world/`, the ODbL dump by absolute URL in `data/<date>/`.

Since REL3 (11.11.2026) a data update is an ordinary commit on top (no force push; old folders are removed only by the owner). A weekly update writes `data/<date>/`,
`world/<date>/world.pmtiles`, extracts the cards into `world/cards-<date>/`, writes `world/manifest-<date>.json` and then both
`latest.json` files.

Data: © OpenStreetMap contributors (ODbL) · Open Charge Map (CC BY 4.0) · GeoNames (CC BY 4.0) and the official open
registries listed in `attribution.json`. The station layer as a database is available under the ODbL
(`data/<date>/odbl-<date>.csv.gz`, with its README).

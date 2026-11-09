# blokvolt-tiles — dev data host for the blokvolt.com world map

Served by GitHub Pages at https://hemptoon.github.io/blokvolt-tiles/ (byte ranges for PMTiles, `Access-Control-Allow-Origin: *`).
Not production: the live host is decided separately (R2). Built by the evdb public layer (`run_public.sh`, K1) and the
pages bundle (`pages_json.py`, K3); see RUNBOOK "Dev previews" in hemptoon/blokvolt-rs.

- `world/<date>/world.pmtiles` — vector tiles, layer `sites`, z0–12.
- `data/<date>/` — cards, manifest, pages bundle and the ODbL dump that the preview workflow of blokvolt-rs downloads.
- `latest.json` — the current date.

History does not grow: every data update replaces the single commit of `main` (force push).

Data: © OpenStreetMap contributors (ODbL) · Open Charge Map (CC BY 4.0) · GeoNames (CC BY 4.0) and the official open
registries listed in `attribution.json`. The station layer as a database is available under the ODbL
(`data/<date>/odbl-<date>.csv.gz`, with its README).

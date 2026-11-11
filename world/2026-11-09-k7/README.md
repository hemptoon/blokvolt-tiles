# K7 — even point density (2026-11-09, task branch k7-density of hemptoon/blokvolt-rs)

Current tiles since 11.11.2026 (REL1): `latest.json` and `world/manifest-2026-11-09.json` point here.
Same data as world/2026-11-09-i1/ (378,784 places, same pid `i` and attributes), other thinning:
- z0–5: tippecanoe -r1 -g2 --drop-densest-as-needed -M 100000 (spacing-based thinning, even grain);
- z6–9: the same with -M 50000;
- z10–12: -B10 as before (every place), plus `k` = max kW rounded (from the i1 cards) for the kW label from z12.
46.3 MB; largest tile 93 KB (z0–7), 81 KB (z8–12). Built with tippecanoe 2.49; tiles spliced by zoom.

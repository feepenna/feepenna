# TRACE-07 assets

Original pixel-art mascot (silver helmet, black visor, navy/black suit, electric-blue details, number 07).

| File | What it is |
|---|---|
| `trace_loop.svg` | Animated SVG used in the profile README (37 frames, 6.2 s loop, 6 fps) |
| `trace_loop.gif` | Same loop as GIF (fallback / preview, on a #0D1117 background) |
| `trace_base.png` | Base sprite, 38x64 px, transparent background |
| `trace_all.png` | All states, one per row, 48x76 px frames |
| `states/trace_<state>.png` | One spritesheet per state, frames side by side |
| `trace_metadata.json` | Frame counts, fps and loop flags per state |

States: idle, thinking, working, success, warning, error, greeting.
Palette (hex): 05060C 0E1224 1C223C 464E64 788096 B6BCCA ECEFF6 123496 1E6EFF 6EAAFF, plus amber E0A030 / 8A5A10 for warning and error only.

## Rules (from the project brief)
- Keep the silhouette, silver helmet, number 07 and the navy/black/silver/electric-blue palette.
- True pixel art on a grid: no anti-aliasing, no gradients, nearest-neighbor scaling only.
- No real F1 team logos, no copied third-party mascots.

## Rebuilding
```bash
pip install pillow
python3 tools/build_loop.py assets/trace/states assets/trace/trace_loop.svg   # SVG + GIF
python3 tools/fix_trace_pack.py <pack-folder>                                  # rebuilds idle + greeting from a pack
```
Edit `SEQUENCE` in `tools/build_loop.py` to change which states play and for how long.

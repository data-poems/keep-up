# Keep Up

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Live Site](https://img.shields.io/badge/live-dr.eamer.dev-brightgreen)](https://dr.eamer.dev/datavis/poems/keep-up/)

3,222 US counties, plotted by how badly rent is eating their residents. One dot per county. The canvas is tilted at the diagonal of your screen so the data runs from top-left (low income, low burden) to bottom-right (high income, high burden) — or the other way around, depending on where you live.

## What it shows

The question driving this is simple: how many hours at minimum wage does it take to cover rent?

Each county dot encodes:
- **X axis**: Median household income (log scale)
- **Y axis**: Rent burden — the share of renters paying 30%+ of income on housing (reversed scale, so higher burden floats up)
- **Size**: Total renter population (sqrt scale)
- **Color**: Blue for manageable burden, red for severe, orange for extreme

Dots with over 40% burden glow. High-burden counties near low-income areas burn the brightest.

The canvas rotates dynamically to match your viewport's diagonal angle, so the data always aligns with the corner-to-corner axis regardless of screen size. Hover a dot to see the county name, rent burden percentage, median income, and estimated hours at minimum wage to cover one month's rent.

## Controls

| Input | Action |
|-------|--------|
| Mouse move | Highlight nearest county |
| Click | Toggle UI visibility lock |
| Touch | Highlight nearest county (mobile) |

## Stack

- D3.js v7 for scales and data loading
- Canvas API for animated particle rendering
- CSS custom properties for the dynamic rotation angle
- Inter + JetBrains Mono for axis labels and data readout
- Census ACS 2022 data via `housing_crisis_merged.csv`

## Files

```
keep-up/
├── index.html                      # Full visualization, inline JS/CSS
├── data/
│   └── housing_crisis_merged.csv   # 3,222 counties, Census ACS 2022
└── social-cards/
    └── keep-up.png                 # 1200x630 Open Graph image
```

## Data

Source: US Census Bureau, American Community Survey 2022 (ACS 5-Year Estimates)

Fields used: median household income, percent of renters paying 30%+ on rent, total renter count, estimated hours at minimum wage required to cover median rent. County-level, all 50 states plus DC.

## Running locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Author

Luke Steuber — [lukesteuber.com](https://lukesteuber.com) — [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com) on Bluesky

Part of the [data poems collection](https://dr.eamer.dev/datavis/poems/) at dr.eamer.dev.

## License

MIT

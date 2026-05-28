# Keep Up — The Burden of Rent

[![Live Site](https://img.shields.io/badge/live-dr.eamer.dev-blue)](https://dr.eamer.dev/datavis/poems/keep-up/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

*How much does it cost to keep up with the Joneses?*

3,222 US counties, plotted by how badly rent is eating their residents. One dot per county. The canvas tilts at the diagonal so the data runs corner-to-corner, low income and crushing burden in one direction, higher income and manageable rent in the other. Dots with over 40% rent burden glow red.

## What It Shows

The question driving this is simple: how many hours at minimum wage does it take to cover rent?

Each dot encodes:

| Encoding | Variable |
|----------|---------|
| X axis | Median household income (log scale) |
| Y axis | Rent burden — reversed, so high burden floats up |
| Size | Total renter population (sqrt scale) |
| Color/glow | Rent burden severity — blue to red, red glows |

Hover any dot to see the county name, rent burden percentage, median income, and estimated hours at minimum wage to cover one month's rent.

The canvas rotates dynamically to match your viewport's diagonal angle, so the data always aligns with the corner-to-corner axis regardless of screen size.

## Controls

| Input | Action |
|-------|--------|
| Mouse move | Highlight nearest county |
| Click | Toggle UI element lock |
| Touch | Highlight nearest county |

## Data

- **Source**: US Census Bureau, American Community Survey 2022 (ACS 5-Year Estimates)
- **File**: `data/housing_crisis_merged.csv`
- **Count**: 3,222 counties — all 50 states plus DC
- **Fields**: Median household income, percent of renters paying 30%+ on rent, total renter count

## Files

```
keep-up/
├── index.html                      # Full visualization, inline JS/CSS
├── data/
│   └── housing_crisis_merged.csv   # 3,222 counties, Census ACS 2022
└── social-cards/
    └── keep-up.png                 # 1200x630 Open Graph image
```

## Tech Stack

D3.js v7 (scales and data loading), Canvas 2D, vanilla JavaScript.

## Running Locally

```bash
python3 -m http.server 8000
# Open http://localhost:8000
```

---

By [Luke Steuber](https://lukesteuber.com) · [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com) · [dr.eamer.dev](https://dr.eamer.dev)

Part of the [data poems collection](https://dr.eamer.dev/datavis/poems/) at dr.eamer.dev.

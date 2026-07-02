# CLAUDE.md — dog-capitals

## What this repo does
Public marketing site for Dog Capital, built with Quarto and deployed to GitHub Pages at jpdecodex.github.io/dog-capitals. Showcases the systematic strategies (ES Core, ETF Core) with backtest research pages for Argentine investors.

## Current state
Live. Design pass shipped (Claude Design spec → Quarto): logo lockup + favicon in the header, homepage rebuilt as two `.program-card`s (Live/Paper tags, 3-stat row), all 7 backtest charts restyled to the Dog Capital palette/rcParams (ink/gray ramp, one green accent, no filled axes, horizontal-only gridlines) via a shared `core/chart_style.py` in es-core-vol-targeting and etf-vol-targeting. ES Core equity/drawdown charts cut from 4 series to 2 (ES Buy & Hold vs Full Strategy); ETF Core's `universe_comparison.png` cut from a stale 9-series chart to 2 (Strategy C7 vs SPY B&H) and Monte Carlo trimmed from 3 configs to just C7 — the config actually offered. `docs/` committed for the first time this pass.

## Next action
Known gap (not urgent): `LOGO.png` is a flattened raster with no vector source — the header lockup and favicons are chroma-keyed crops with soft edges. Get a true vector (SVG/EPS) or 2000px+ transparent PNG from the original source and redo the crops before any print/large-format use.

## Architecture decisions
- Quarto + GitHub Pages (`docs/` build output), no JS framework — consistent with the rest of the ecosystem (see playbook ADR 005).
- Programs are separate `.qmd` pages under `programs/`, research write-ups under `research/`.
- Site scope is public-facing only. Venue names for the systematic programs (IBKR, IOL, Balanz) are fine to state — standard track-record transparency. Never: prop-firm/ladder mechanics, real balances, entry/exit levels, or partner names (those live in es-core-vol-targeting / etf-vol-targeting).

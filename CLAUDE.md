# CLAUDE.md — dog-capitals

## What this repo does
Public marketing site for Dog Capital, built with Quarto and deployed to GitHub Pages at jpdecodex.github.io/dog-capitals. Showcases the systematic strategies (ES Core, SPY Core) with backtest research pages for Argentine investors.

## Current state (2026-07-09)
Repo reorganized this session: `etf-core.qmd` renamed to `spy-core.qmd` (SPY Core = the multi-asset SPY/GLD/IBIT program, named after its core instrument like ES Core is) and its stale execution-layer copy (Balanz-only, pre-IOL) corrected. `handoff/` (gitignored duplicate delivery) deleted, fully superseded by top-level `brand/`. The Notion drafting room (page "Dog Capital", subpages Home/Active Strategies/About Us/Research Center/Enquiries/Legal) is the copy source of truth — see `[[dog_capital_site_architecture]]` and `[[strategy_state]]` in the user's memory for details not repeated here.

Nav trimmed to only working links (Active Strategies) — About Us, Research Center, and Enquiries were linked from nav but had no backing pages (or an empty stub), so those links were removed rather than left broken.

Homepage (`index.qmd`) rebuilt using Notion's Home copy: hero, ES Core — Futures / SPY Core — ETFs cards side-by-side in a grid (`.program-grid`, deliberately not tabs — both strategies stay visible at once, matching the site's transparency positioning; Notion's mock used click-to-switch tabs but that was reconsidered). Each card shows one Live/Paper Results stat block (labeled "Paper Results Overview" for ES Core, "Live Results Overview" for SPY Core; both currently "Populating") plus a single compact backtest reference line (`.backtest-ref`, e.g. "Backtest CAGR 9.80% · 04-09-2001 to 03-07-2026") — the full 10-metric backtest table stays exclusively on each program's dedicated page, no duplication.

**Open: homepage card visual style needs a redesign pass.** User is not satisfied with the current look (sans-serif, fully-bordered box, muted-gray, plain-text links) and referenced a friend's site with a distinctly different visual language: serif typography, a small-caps letter-spaced eyebrow section label ("ACTIVE PROGRAMS"), a left accent border instead of a full box border, and outlined button-style links ("STRATEGY DOCUMENT →", "PERFORMANCE ATTRIBUTION →") instead of plain text links. Not implemented — this is the next thing to pick up, before building any other section.

**Working process for this rebuild: one section at a time, user-directed.** Don't build the next section (About Us, Research Center, Enquiries, or a redesigned ES Core/SPY Core program page) speculatively — ask which one first.

## Next action
1. Card visual redesign (see "Open" note above) — serif type, eyebrow label, left accent border, button-style links. Get the reference image/site again from the user if not carried forward.
2. Known gap (not urgent): `LOGO.png` is a flattened raster with no vector source — the header lockup and favicons are chroma-keyed crops with soft edges. Get a true vector (SVG/EPS) or 2000px+ transparent PNG from the original source and redo the crops before any print/large-format use.

## Architecture decisions
- Quarto + GitHub Pages (`docs/` build output), no JS framework — consistent with the rest of the ecosystem (see playbook ADR 005).
- Programs are separate `.qmd` pages under `programs/`, research write-ups under `research/`.
- Brand reference material (Claude Design manual, visual system spec) lives in top-level `brand/` — deliberately outside `docs/` (Quarto's output-dir gets swept on render; anything untracked there is at risk).
- Site scope is public-facing only. Venue names for the systematic programs (IBKR, IOL, Balanz) are fine to state — standard track-record transparency. Never: prop-firm/ladder mechanics, real balances, entry/exit levels, or partner names (those live in es-core-vol-targeting / spy-core-vol-targeting).

# CLAUDE.md — dog-capitals

## What this repo does
Public marketing site for Dog Capital, built with Quarto and deployed to GitHub Pages at jpdecodex.github.io/dog-capitals. Showcases the systematic strategies (ES Core, ETF Core) with backtest research pages for Argentine investors.

## Current state
Live. Homepage lists ETF Core and ES Core programs. ETF Core research page has full 25yr backtest metrics (QQQ dropped, SPY buy & hold comparison added). Site identity redesigned around Argentina/SPY-only positioning; RR Capital-style skeleton (custom CSS, inline nav, section divs, program cards).

## Next action
- Research page for ES Core is still a placeholder — add content once live performance data exists.
- Axi Select program stays hidden until partner (Fran) agrees to go public.
- Swap in real equity-curve charts once live performance data is available (currently backtest-only).

## Architecture decisions
- Quarto + GitHub Pages (`docs/` build output), no JS framework — consistent with the rest of the ecosystem (see playbook ADR 005).
- Programs are separate `.qmd` pages under `programs/`, research write-ups under `research/`.
- Site scope is public-facing only — no real balances, broker names, or private strategy internals (those live in es-core-vol-targeting / etf-vol-targeting).

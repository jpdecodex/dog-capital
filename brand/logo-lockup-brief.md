# Dog Capital — logo lockup fix (brief for Claude Design)

**Status:** drafted 2026-07-10, not yet sent/run through Claude Design.

## Prompt

I need a fix to the Dog Capital logo lockup — an existing asset, not a new design from scratch.

**Current asset** (`LOGO-lockup.png`, 562×270px, flattened raster, no vector source): "DOG" on one line — with a dog-head silhouette isotype embedded inside the "O" — stacked above "CAPITAL" spelled out in smaller letter-spaced serif small caps on a second line below it.

**The problem:** it's stacked across two lines. It needs to become a single horizontal line: **"DOG CAPITAL"** reading left to right on one baseline.

**What to keep unchanged:** the isotype treatment inside the "O" of "DOG" — the dog-head silhouette (see attached `brand/logo-mark.png`, the standalone circular version of the same mark) stays exactly where and how it currently sits, integrated into the letterform. Don't redesign the mark itself or its relationship to the "O."

**What to change:** "CAPITAL" needs to sit inline on the same baseline as "DOG," properly typeset as one cohesive wordmark — not just shrunk and pasted next to it. Keep it in the same spirit as its current treatment (smaller scale than "DOG," letter-spaced serif small caps) but re-spaced/re-kerned to read naturally as a single-line lockup.

**Deliverable:** true vector (SVG, EPS, or AI) preferred. If vector isn't possible, a high-resolution (2000px+ width) transparent PNG — not another flattened low-res raster like the current one. This also closes a pre-existing gap: the current asset has soft, chroma-keyed edges from having no vector source.

**Usage context:** this will be the centered logo in the site header of dog-capitals (a Quarto-built systematic-trading research site) — so it should read as a balanced, self-contained horizontal lockup, not one designed assuming left-alignment or cropping.

Attach: `LOGO-lockup.png` (current asset) and `brand/logo-mark.png` (isotype reference).

## Why this exists

`Claude Code` (this repo's coding agent) can't safely produce this itself — the current lockup is a single flattened raster with no isolated font or vector layers, so cropping "DOG" out and re-typesetting "CAPITAL" next to it in code risks a visible font/weight/baseline mismatch. This needs an actual design pass, not an image-manipulation hack.

## Site-side change still pending

Once the new lockup asset exists, the homepage header (`index.qmd`) also needs the logo re-centered — it's currently left-aligned (`#site-header img`, `display: block` with no centering). Not done yet; waiting on the new asset first.

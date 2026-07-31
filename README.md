# What Your Country Can Do For You

A civic calculator that runs Kennedy's line in reverse: pick any line item from
America's recent war budget — the $150B reconciliation defense package, Golden
Dome, one Patriot battery — and price it in the things a country does for its
people: SNAP years, pre-K seats, affordable apartments, teacher salaries.

**One self-contained file.** No build step, no dependencies, no tracking.
Open `index.html` or serve the folder statically:

```bash
python3 -m http.server 4173 --directory .
```

## Features

- **Side-by-side ledgers** — the war ledger (sticky, left) and the people's
  ledger (right) share the screen on desktop, so checking a line item updates
  the trade-offs in view; stacked on mobile.
- **The war ledger** — 13 real appropriations from recent legislation (FY25
  NDAA, the 2025 reconciliation act, the April 2024 supplemental, CBO/GAO
  program estimates), filterable by sector (missile defense, aircraft, ships,
  nuclear, foreign aid, packages), with a running "receipt" (total,
  per-household, per-congressional-district).
- **Ask the ledger** — a prompt box that prices anything from a built-in
  price book of 150+ items ("how many diapers?", "years of rent", "MRI
  scans"), plus six browsable categories of tappable items — Household,
  Animals (yes, horses), Luxury, Homes & property, Food & drink, Fun &
  games. Instant, offline, no API calls.
- **An uncluttered default** — "The headlines" shows ten flagship trade-offs;
  a "+13 more" tile expands to everything, and policy filters show full
  categories.
- **The people's ledger** — 23 trade-off cards (18 unit-price cards + 5
  "runs the whole program for X" duration cards), filterable by policy type,
  each with an animated isotype dot grid and a named federal source.
- **Perspective in dots** — your selection and the annual budgets of SNAP,
  NIH, Title I, Head Start, NCI, the Park Service, CPB, and the NEA drawn to
  one scale: each dot = $1B. The NEA is one faint dot.
- **Employment dividend** — jobs-per-dollar multipliers vs. military spending
  (Peltier, Costs of War Project, 2025).
- Light ("bond paper") and dark ("engraved plate") themes; respects
  `prefers-reduced-motion`; CVD-validated category palette.

## Data

All figures are rounded public numbers, compiled July 2026 — sources are
linked in the page's "Sources & further reading" section (CBO, GAO, CRS,
USDA, NEA, NIEER, College Board, HHS, HUD, KFF, MACPAC, EPA, Census,
CRFB, Costs of War). Method caveats are stated on the page: time spans
differ and are labeled, unit costs are national averages, comparisons are
illustrative.

To update numbers, edit the `DEFENSE`, `UNITS`, `PROGRAMS`, `ANNUALS`,
`JOBS`, and `CATALOG` arrays at the top of the `<script>` block in
`index.html`.

## QA hooks

- `?jump=<section-id>` — land instantly on a section with all motion completed
- `?solo=<section-id>` — render one section only (`workbench`, `scale`,
  `jobs`, `method`, `colophon`; `ledger`/`tradeoffs` alias to `workbench`)

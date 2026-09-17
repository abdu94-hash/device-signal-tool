# Changelog

This file records every notable change to the companion site and web tool for _Signal Management in Medical Device Vigilance_. Versions follow [Semantic Versioning](https://semver.org/).

## [1.1.0] - 2026-09-17

### Added
- `lab/index.html` — Case Lab: the ten-step signal lifecycle with all eight book cases solved step by step (80 decide-then-reveal steps, live-computed working, per-case and overall scores held in memory), a "Your Signal" workbench that runs the user's own data through the same ten steps and produces a printable/downloadable signal record, and an interactive process map.
- Links to the Case Lab from the landing page and the calculators.

## [1.0.0] - 2026-09-16

### Added
- Landing page (`index.html`) with a book overview, a description of the site's three parts, the toolkit index T-1 to T-24 with chapter and format, a zip download link, and a change log.
- Web tool (`tool/index.html`), one self-contained file with six modules:
  - Trend screen: p-chart limits, the 2-of-3 run rule, a standardized CUSUM, exact binomial tail probabilities, and a chart (Chapter 8).
  - Disproportionality 2×2 (PRR and ROR with 95% intervals, expected count, Yates chi-square, optional company rule) and registry O/E (exact Poisson interval, exact 95% and 99.8% funnel limits, funnel plot) (Chapter 9).
  - Time-to-failure life table with Kaplan–Meier survival and Greenwood intervals (Chapter 10).
  - Five-domain prioritization with bands, the floor rule, urgency triggers and recorded overrides (Chapter 13).
  - Risk-file update on the illustrative 5×5 matrix, with an exact interval, the P1/P2 split and a labeled target (Chapter 18).
  - Printable decision record that keeps the conclusion separate from the status (Chapters 19 and 23).
- A "Load book example" button in every module. Every field starts empty.
- `README.md`, `LICENSE` (book content all rights reserved; tool code MIT), and `.nojekyll`.

### Quality checks
- Automated browser tests confirmed the book's figures for Suturex, Glucalyn, Tessora and Kestran. They also confirmed that clearing a field produces a validation message and removes the earlier result, that the page makes no external requests, uses no storage and logs no console errors, that printing shows only the record, and that the layout works at desktop and 390 px mobile widths.

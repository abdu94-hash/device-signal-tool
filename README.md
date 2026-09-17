# Device Signal Tool: companion site

Companion site for **_Signal Management in Medical Device Vigilance_** by Dr. Hafez Selim, MD, PhD (Selim Medical Press, Medical Device Safety Series, Book 5, © 2026).

Live site: **https://abdu94-hash.github.io/device-signal-tool/**

## Contents

| Path | What it is |
|---|---|
| `index.html` | Landing page: about the book, the toolkit index (T-1 to T-24), a link to the zip file, and the change log |
| `lab/index.html` | Case Lab: the full ten-step process with the eight book cases solved, plus a workbench for your own signal. Self-contained, no storage |
| `tool/index.html` | The web tool. One self-contained HTML file with inline CSS and JavaScript, no external requests, no storage and no analytics |
| `toolkit/` | The 24 toolkit files and `Device_Signal_Toolkit.zip` |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |
| `CHANGELOG.md`, `LICENSE` | Change history and license terms |

## Web tool modules

1. **Trend screen** (Chapter 8): expected count, SD, 2σ and 3σ limits, the 2-of-3 run rule beyond 2σ, a standardized CUSUM with user-set k and h, exact binomial tail probabilities, and an SVG chart.
2. **Disproportionality and registry O/E** (Chapter 9): PRR and ROR with log-method 95% intervals, the expected count, Yates chi-square, and an optional company screening rule. O/E with an exact Poisson 95% interval, exact funnel limits at 95% and 99.8%, the normal-approximation comparison, and a funnel plot.
3. **Time to failure** (Chapter 10): a life table with Kaplan–Meier survival, Greenwood linear 95% intervals truncated to 0–100%, hazard per interval, the crude proportion, and a chart.
4. **Prioritization** (Chapter 13): five domains scored 1–5 against the chapter's anchors, with a required rationale for each. Bands A/B/C, the floor rule (severity 5 with detectability 4 or 5 gives Band B at least), urgency triggers (Band A), a one-band override (a reason is required, and a downward move also needs the chair's signature), and a sensitivity check.
5. **Risk-file update** (Chapter 18): the illustrative 5×5 company matrix. It shows the probability band and region before and after the signal, with an exact Poisson interval, the P1/P2 split, and an optional post-control target labeled as a target.
6. **Decision record** (Chapters 19 and 23): signal-record and FSCA-decision fields. It generates a printable record that keeps the **conclusion** (a finding) separate from the **status** (administrative), and it enforces consistency rules. Printing uses print CSS through the Print button or the browser's own print command.

Every module has a **Load book example** button (Suturex, Glucalyn, Tessora, Kestran, Glucalyn, Glucalyn, Suturex). Otherwise every field starts empty. An empty field is never read as zero, validation errors are listed with links to the fields, and any previous result is cleared when an error appears.

### Verified against the book

| Case | Expected | Tool |
|---|---|---|
| Suturex trend | E 20, SD 4.47, limits 28.9 / 33.4, CUSUM 6.17 at Y4 M4 | matches |
| Glucalyn 2×2 (30 / 570 / 90 / 8,910) | PRR 5.0 (3.34–7.50), ROR 5.21 (3.42–7.94), χ² 69.7 | matches |
| Tessora O = 48, E = 26 | O/E 1.85 (1.36–2.45); 95% limits 17–36; 99.8% limits 12–43; normal 41.8 | matches |
| Kestran life table | 97.7% (97.1–98.4) at year 5; 2.3% cumulative; crude 1.2% | matches |
| Glucalyn prioritization | 22 of 25, Band A | matches |
| Glucalyn risk file | 1 in 20,000 (P3, ALARP) → 1 in 2,000 (P4, unacceptable); interval 2.2–13.1 events | matches |

The statistics (log-gamma, regularized incomplete gamma, Poisson quantiles, gamma inverse, exact binomial tail) are implemented in plain JavaScript inside `tool/index.html`.

## Publishing

1. Create the public repository `abdu94-hash/device-signal-tool` and push these files to `main`.
2. Under **Settings → Pages**, choose "Deploy from a branch", then `main` and `/ (root)`.
3. Add the 24 toolkit files and `Device_Signal_Toolkit.zip` to `toolkit/`, using the file names linked from `index.html`.

## Disclaimer

This is an educational tool. It is not validated software and not a controlled quality record. Every score, band, anchor, matrix, threshold and response time is an example of a company design, not a regulatory requirement. All cases are fictional composites with illustrative numbers.

## License

The book content is all rights reserved, and the tool code is released under the MIT License. See [LICENSE](LICENSE).

# Friday 20 November 2026 — World News Front Page (make.fun bounty entry)

[![make.fun · news-image-20261120](https://make.fun/badge/news-image-20261120.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![rank](https://make.fun/badge/news-image-20261120/Userhacking935/news-image-20261120/rank.svg)](https://make.fun/bounty/news-image-20261120/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![reward](https://make.fun/badge/news-image-20261120/Userhacking935/news-image-20261120/reward.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)

This entry deterministically generates a 1024×1024 newspaper front page summarizing the world's news from Friday 20 November 2026.

## Overview & Editorial Structure

- **40 Stories Across 7 Regions**: Full coverage encompassing Europe (9), Asia-Pacific (9), Americas (8), Middle East (4), Africa (4), Oceania (4), and Global (2).
- **Cream Newspaper Paper**: `#F7F1DE` background styling with classical newspaper typography.
- **Eyebrow & Serif Masthead**: "Friday 20 November 2026" with italic sub-headline highlighting the day's major events.
- **6-Box KPI Strip**: Highlighting verified key metrics of the day (fatalities across Ukraine, Akvan shelter evacuations, Taiex index close, UK-EU youth visas, S&P 500 move, Glenn Phillips score).
- **Region Bar**: 7 colored category chips showing story counts per region, summing exactly to 40.
- **3 Hero Stories with Realistic Photo Illustrations**:
  1. *Kyiv, Ukraine*: Russian missiles hit three Kyiv bridges overnight barrage.
  2. *Odisha, India*: Cyclone Akvan landfall near Gopalpur.
  3. *Taipei / Seoul / Tokyo*: AI stock market sell-off sinks Asian tech shares.
  Illustrated using center-cropped, LANCZOS-downscaled realistic photo panels sliced from `assets/realistic/media-generation-hero-triptik-realistis-0-*.webp`.
- **10 Mid Stories (2 Rows of 5)**:
  - Row 1: UK-EU diplomacy reset, COP31 climate talks, Poland missile debris, BepiColombo Mercury arrival, Italy general strike.
  - Row 2: Kenya first oil drilling, Bukele third term filing, Phillips 118 cricket century, Japan 2.3% inflation, pancreatic cancer pill trial.
  Illustrated using realistic photo panels from `assets/realistic/media-generation-mid-baris1-realistis-0-*.webp` and `assets/realistic/media-generation-mid-baris2-realistis-0-*.webp`.
- **Bottom Section**:
  - *"WHERE IT HAPPENED" World Map*: Drawn with vector continent polygons and numbered pins 1–13 matching each illustrated story.
  - *"ALSO ON FRIDAY 20 NOVEMBER"*: 27 one-line briefs in 2 columns (stories 14–40) with number, place, headline fact, and source attribution.
- **DATE CHECK Box**: Red-bordered box explicitly documenting stories deliberately omitted because they broke on Thursday 19 November (Shenzhen summit itself, ICJ Myanmar ruling, Anthropic IPO day one, PIF Tower strike, Van Gogh auction, Crimean Bridge attack, GTA VI midnight launch).
- **Attribution Footer Line**: Sources named beside each story.

## Technical Specifications

- **Runtime**: Python 3.13, Pillow 10.2+ and Python standard library only.
- **Strictly Deterministic**: No random numbers, no system timestamps, no network calls, no environment-dependent rendering.
- **Font Rendering & Overflow Prevention**:
  - Fonts loaded from `./fonts/` first (`DejaVuSerif-Bold.ttf`, `DejaVuSerif.ttf`, `DejaVuSans-Bold.ttf`, `DejaVuSans.ttf`).
  - Font sizes strictly maintain legibility: Heroes headline 13.5px / deck 12px; Mids headline 11px / deck 10.5px; Briefs 9.5px.
  - Programmatic bounding box and text length assertions ensure zero text overflow.
- **Dual Output**: Identical PNG bytes written simultaneously to `/output/entry.png` and `./entry.png`.
- **Image Optimization**: Saved with `optimize=True, compress_level=9, no metadata`.
  - Dimensions: 1024 × 1024 px.
  - File Size: ~711 KB (well below the 1 MiB bounty limit).

## Running the Script

To generate the image:

```bash
python3 main.py
```

To verify determinism and output integrity:

```bash
python3 -c "
import hashlib, subprocess

subprocess.run(['python3', 'main.py'], check=True)
with open('entry.png', 'rb') as f:
    h1 = hashlib.sha256(f.read()).hexdigest()

subprocess.run(['python3', 'main.py'], check=True)
with open('entry.png', 'rb') as f:
    h2 = hashlib.sha256(f.read()).hexdigest()

assert h1 == h2, 'Runs produced different bytes!'
print('PASS: Identical SHA-256 =', h1)
"
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=n4rj7cxc&utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120) · AI agents build software for cash rewards</sub>

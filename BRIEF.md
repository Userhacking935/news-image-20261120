# BRIEF — make.fun bounty news-image-20261120 (DRAFT, DO NOT SUBMIT)

## Goal
Build a local draft entry for the make.fun bounty "Sum up 20 November's world
news in one image" (https://make.fun/bounty/news-image-20261120).
Deliverable in THIS directory: `main.py` (Python 3.13, Pillow only, stdlib +
Pillow) that deterministically draws the front-page image, plus the generated
`entry.png` (1024x1024, < 1 MiB).

DO NOT submit anything to make.fun. DO NOT create a GitHub repo. DO NOT
upload anything. DO NOT use the network from main.py. Just build it locally
and verify it. The user will review the image here first.

- Reward: $250 total; 1st $50, 2nd $30, 3rd $15, 4th-10th $5, 11th-50th $3.
- Deadline: 2026-11-22T00:00:00Z (Sun 22 Nov 2026 07:00 WIB). Now is Fri 21 Nov
  2026 ~13:00 WIB, so ~18 hours left.
- Judge: an AI judge that can see images compares entries two at a time and
  picks the one that best sums up the day's world news. The judge has NO news
  feed: it judges as a careful picture editor, by what the image itself shows.
  Entries rank by win rate. 19,823 submissions already; top 10 are all 12W-0L,
  win rates 99.08%-99.21% — extremely close, so density + legibility + date
  discipline decide.
- Entry rules (for later, not now): program at main.ts/main.py in repo root,
  writes one image to /output/entry.png; image whole PNG/JPEG, at most 1 MiB,
  1024x1024; no network; program runs twice and both runs must write the same
  bytes; at most 10 submissions/day, 20 total; last submission is final.

## What the top 10 do (analysed from their actual judged images, saved in
../top10/rank01..rank10-*.webp — look at them if you can open images)
Winning formula, all top 10 share it:
- Newspaper front page, cream paper (#F7F1DE-ish), 1024x1024.
- Huge serif masthead "Friday 20 November 2026", italic sub-headline naming
  the 4 biggest stories.
- KPI strip: 6 big numbers with small captions (deaths, evacuees, market %,
  visas, etc.).
- Region bar: coloured chips with story counts per region, summing to the
  total story count.
- 3 large HERO stories with original drawn illustrations (bridges + missile
  arcs at night; cyclone spiral over a map; falling stock chart), each with a
  numbered kicker (place - topic), bold headline, 2-3 line deck, source in
  brackets.
- 10 smaller illustrated stories in 2 rows of 5, each with a small drawn
  illustration (flag, chart, globe, etc.), numbered kicker, headline, 1-2
  line deck, source.
- Bottom: "WHERE IT HAPPENED" world map with numbered pins matching the
  illustrated stories, plus "ALSO ON FRIDAY 20 NOVEMBER" list of the
  remaining stories, numbered, one line each, in 2 columns.
- "DATE CHECK" red-bordered box at the bottom: stories deliberately LEFT OUT
  because they were first reported Thursday 19 Nov, not Friday 20 Nov.
  This date discipline is a visible edge the top entries all use.
- Every story is attributed (Reuters, AP, BBC, AFP, IMD, etc.) and flagged
  where uncertain: "officials say", "reported", "estimate", "ongoing".
- Story counts in top 10: 33, 33, 36, 33, 38, 36, 36, 35, 36, 36.
  OUR EDGE: 40 stories, 7 regions — more than any top-10 entry — while
  staying legible. Do NOT go above 40: legibility is what the judge rewards.

## The 40 stories (use EXACTLY this list, in this order, with these numbers —
they are the consensus of the top-10 entries and same-day news reports;
where numbers differ between sources I picked the most-repeated one and
flagged it as reported/officials say)
Regions must total: Europe 9, Asia-Pacific 9, Americas 8, Middle East 4,
Africa 4, Oceania 4, Global 2 = 40. The region bar MUST show exactly these.

### HEROES (3 large, stories 1-3)
1. [Europe] KYIV, UKRAINE - WAR. Headline: "Russian missiles hit three Kyiv
   bridges". Deck: "An overnight barrage of about 110 missiles and 400 drones
   killed at least 8 people across Ukraine and cut power and water in the
   capital. (Kyiv Independent, BBC)". Illustration: night skyline, 3 bridges
   over a river, missile arcs, fires.
2. [Asia-Pacific] ODISHA, INDIA - CYCLONE. Headline: "Cyclone Akvan comes
   ashore in eastern India". Deck: "The storm crossed the coast near Gopalpur
   from about 8 am after more than 300,000 people were moved to shelters.
   No deaths were reported. (IMD, The Hindu)". Illustration: map of Odisha
   coast + cyclone spiral, "Landfall - 8 am".
3. [Asia-Pacific] TAIPEI - SEOUL - TOKYO - MARKETS. Headline: "AI sell-off
   sinks Asia's stock markets". Deck: "Taiwan's index fell 6.2% to end its
   worst week since 1991. Seoul lost 5.2% and Tokyo 5.1% as chipmakers led
   the slide. (Al Jazeera, Anadolu)". Illustration: falling red chart with
   Taipei -6.2%, Seoul -5.2%, Tokyo -5.1%, Hong Kong -1.9%.

### MID STORIES (10 small illustrated, stories 4-13)
4. [Europe] BRUSSELS - DIPLOMACY. "UK and EU seal a 'reset' deal". Deck:
   "Food trade, youth visas, carbon link. 100,000 youth visas a year.
   (Reuters)". Illustration: UK + EU flags.
5. [Europe] ANTALYA - CLIMATE. "COP31 reaches its last day with no deal".
   Deck: "The draft text leaves out fossil fuels. Talks run past Friday.
   $120bn adaptation finance unresolved. (UN News, Reuters)". Illustration:
   globe + thermometer, "FINAL DAY".
6. [Europe] EASTERN POLAND - SECURITY. "Russian cruise missile lands in
   Poland". Deck: "A KH-101 was found in a field; two airports paused. No
   one hurt. (Reuters)". Illustration: missile + map, "KH-101".
7. [Global] SPACE. "BepiColombo reaches Mercury after 8 years". Deck:
   "ESA/JAXA probe ends 6bn-mile trip; orbit insertion set for Saturday.
   (ESA, BBC)". Illustration: Moon/Mercury + spacecraft.
8. [Europe] ITALY - LABOUR. "General strike over Italy's budget". Deck:
   "Workers and students march; about 100 rallies planned. (CGIL, AFP)".
   Illustration: marching figures, "SCIOPERO".
9. [Africa] TURKANA, KENYA - ENERGY. "Kenya starts drilling its first oil".
   Deck: "First crude is due on 1 December. (allAfrica)". Illustration:
   oil derrick at sunset.
10. [Americas] SAN SALVADOR - POLITICS. "Bukele files to run for a third
    term". Deck: "The vote is on 28 February 2027. (AP)". Illustration:
    ballot box, "3RD BID".
11. [Oceania] WELLINGTON - CRICKET. "Phillips hits 118 against India".
    Deck: "First NZ batter with centuries in all three formats in a year.
    Nicholls 175 not out; NZ 368. (ICC)". Illustration: cricket bat + ball,
    "118".
12. [Asia-Pacific] TOKYO - ECONOMY. "Japan's inflation picks up to 2.3%".
    Deck: "October CPI; a December rate rise stays in view. (Reuters)".
    Illustration: rising bar chart, "2.3%".
13. [Global] HEALTH - SCIENCE. "Cancer pill shrinks pancreatic tumours".
    Deck: "60.7% respond in an early trial; tumours gone from scans in
    1 in 12 patients. (Reuters)". Illustration: pill capsule, "60.7%".

### ALSO ON FRIDAY 20 NOVEMBER (27 one-line briefs, stories 14-40)
14. [Middle East] Iraq: Iraqi army enters a militia stronghold, Jurf
    al-Sakhar. (Reuters)
15. [Americas] Washington: Senate votes 51-48 to block a limit on Trump's
    Iran war powers. (AP)
16. [Americas] California: state probes Nvidia over chips in China; SEC
    probe reported. (Reuters)
17. [Europe] Lviv: a Russian strike on a railway station kills 2. (BBC)
18. [Asia-Pacific] Shenzhen: Trump, Xi and Putin joint declaration
    published Friday. (Xinhua)
19. [Asia-Pacific] New Delhi: Pakistan's prime minister visits, first
    since the May 2025 clash. (PTI, Dawn)
20. [Middle East] Gaza: Israeli strikes kill 6 despite the truce,
    rescuers say. (Al Jazeera)
21. [Middle East] Yemen: coalition strikes Houthi-held Hodeidah. (Reuters)
22. [Middle East] Hormuz: tanker set ablaze off Oman; no casualties;
    Iran's Guards blame a mine. (UKMTO)
23. [Africa] Malawi: fuel crisis brings night-long petrol queues.
    (Al Jazeera)
24. [Asia-Pacific] Seoul: ruling party moves to impeach the top judge.
    (Korea Herald)
25. [Asia-Pacific] Seoul: 111 students caught cheating in the Suneung
    exam. (Officials say)
26. [Asia-Pacific] Beijing: China holds its loan rates at 3.0% and 3.5%.
    (PBOC, Reuters)
27. [Americas] Games: GTA VI sales top $2.36bn, a launch record; about
    24m copies sold. (Sensor Tower estimate)
28. [Oceania] Sydney: retailer General Pants enters administration. (ABC)
29. [Asia-Pacific] Hong Kong: Hang Seng about 20% off its January peak.
    (AP)
30. [Africa] Ethiopia: US warns of troops massing on the Eritrea border.
    (US State Dept)
31. [Oceania] Tonga: drought emergency declared as El Nino bites. (RNZ)
32. [Africa] Senegal: migrant boat capsizes off Senegal; 4 dead, dozens
    missing. (Al Jazeera)
33. [Europe] Berlin: young Germans rally against conscription. (dpa)
34. [Americas] Mexico City: Sheinbaum leads the Revolution Day parade.
    (AP)
35. [Europe] Turin: ATP Finals group stage ends; Alcaraz and Medvedev
    through. (ATP)
36. [Americas] Florida: floods spread north after 17+ in of rain. (AP)
37. [Americas] Washington: Democrats stay divided at conference despite
    midterm wins. (AP)
38. [Oceania] Sydney: Australian shares fall 1.8% in the sell-off.
    (Reuters)
39. [Europe] Turin: ATP backs a plan to lift player pay past $350m.
    (Anadolu)
40. [Americas] Cincinnati: Fiona the hippo dies days after swallowing a
    hat. (AP)

## KPI strip (6 boxes, top of page)
- 8 | killed across Ukraine, PM says
- 300,000+ | people moved to shelters before Akvan
- -6.2% | Taiwan's Taiex at Friday's close
- 100,000 | youth visas a year in the UK-EU deal
- -3.7% | S&P 500 on Friday
- 118 | Phillips against India

## DATE CHECK box (bottom, red border)
"DATE CHECK — Left out as Thursday 19 November's news, not shown as
Friday's: the Trump-Xi-Putin Shenzhen summit itself; the ICJ's Myanmar
genocide ruling; Anthropic's IPO day one ($97.17 close); the Houthi strike
on Riyadh's PIF Tower; the $190.4m Van Gogh sale; the Crimean Bridge attack;
GTA VI's midnight launch."
Footer line: "Every story here happened, or was first reported, on Friday
20 November 2026. Sources named beside each story - original drawings."

## Layout (1024x1024, cream paper #F7F1DE, margins 28px)
- Eyebrow: "THE WORLD IN ONE DAY" left; "40 STORIES - 7 REGIONS - EVERY ONE
  DATED FRIDAY 20 NOVEMBER 2026" right; small red caps.
- Masthead: "Friday 20 November 2026", huge serif bold, centred.
- Sub-headline (italic serif): "Russian missiles hit Kyiv's bridges -
  Cyclone Akvan strikes India - An AI sell-off sinks Asia's markets -
  UK and EU seal a deal"
- KPI strip: 6 boxes, big number + 2-line caption.
- Region bar: coloured chips: Europe 9, Asia-Pacific 9, Americas 8,
  Middle East 4, Africa 4, Oceania 4, Global 2.
- Hero row: 3 columns. Each: drawn illustration (~300x150), red label
  chip, numbered kicker "1 KYIV, UKRAINE - WAR", bold headline, deck.
- Mid rows: 2 rows x 5 columns. Each: small drawn illustration
  (~185x78), numbered kicker, bold headline (2 lines max), 2-line deck.
- Bottom section: left "WHERE IT HAPPENED" world map (simple continents
  drawn with polygons) with numbered pins 1-13 for the illustrated stories;
  right "ALSO ON FRIDAY 20 NOVEMBER - 27 MORE STORIES" in 2 columns,
  one line per brief (number in red + place bold + short text + source).
- DATE CHECK box, then the footer line above.
- NOTHING may overflow its box. All text must fit. Use Pillow
  font.getbbox/getlength to wrap text and assert every block fits; if a
  deck does not fit, shorten the deck (never shrink below 9.5px for briefs,
  10.5px for mids, 12px for heroes).

## Technical spec for main.py
- Python 3.13, Pillow only (plus stdlib). No network, no random, no time,
  no timestamps, no environment-dependent output. Same input -> same bytes.
- Fonts: load from fonts/ in this repo first (DejaVuSerif-Bold.ttf,
  DejaVuSerif.ttf, DejaVuSans-Bold.ttf, DejaVuSans.ttf — already copied
  here), fall back to /usr/share/fonts/truetype/dejavu/ same names, then
  Pillow's load_default().
- main.py writes the PNG to /output/entry.png (create /output if needed)
  AND to entry.png next to main.py, from the SAME in-memory bytes.
  Save with Pillow, optimize=True, compress_level=9, no metadata.
- Verify after building: run `python3 main.py` TWICE to two different
  output dirs and compare sha256 (must be identical); check size
  1024x1024 and file < 1 MiB (if over, save as JPEG quality 88 instead —
  but PNG with flat colours should be well under 1 MiB); check every
  text block fits (programmatic bbox assertions, fail loudly if not).
- Keep the code readable and self-contained in one file main.py. All 40
  stories live as data inside main.py (the agent writes them in; the brief
  above is the source of the facts).
- Also write a short README.md in this directory describing the entry and
  how to run it (for later submission; no GitHub yet).
- Entry title (for later): "Friday 20 November 2026: 40 stories, 7 regions
  - Kyiv bridges hit, Cyclone Akvan landfall, Asia's AI sell-off, UK-EU deal"

## Report back when done
- entry.png path, its size in bytes, sha256 of two runs (must match),
  dimensions, and a short note on what you drew and any story/layout
  compromise you had to make. Do NOT submit anything anywhere.

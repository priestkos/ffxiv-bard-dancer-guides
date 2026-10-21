# FFXIV Bard &amp; Dancer Guides

Two cinematic, self-contained guide sites for the Physical Ranged DPS jobs in
*Final Fantasy XIV: Dawntrail* — plus a landing page that splits between them.

Every page is a **single HTML file with its CSS and JavaScript inline**. No fonts,
scripts, images, stylesheets or CDNs are fetched from anywhere: the three files
work offline, from a USB stick, or from `file://`, and there is nothing that can
break when a remote host goes down.

## The sites

| Page | Theme | What it covers |
|---|---|---|
| [`index.html`](index.html) | Green + red diptych | Landing page. Pick a path; the seam follows the pointer. |
| [`sites/bard-guide.html`](sites/bard-guide.html) | Shades of green | **Bard — The Resonance.** Core mechanics, the 11-GCD opener, the song cycle, 3-6-9 vs 3-3-12, priority ladders, AoE swaps, level-sync floors. |
| [`sites/dancer-guide.html`](sites/dancer-guide.html) | Shades of red | **Dancer — The Ember Waltz.** Dance steps and the 1.5s weave lock, the Level 90–100 kit, the −15.5s pre-pull and burst table, the 30/60/120 cadence, the nine-rank filler matrix, Dance Partner tiers, gearing and raid utility. |
| [`sites/scholaranatomy/`](sites/scholaranatomy/) | Dark neutral | **Scholar — Five Machines.** Interactive isometric figures for Deployment Tactics, Aetherflow, Faerie Gauge, Summon Seraph, and Chain Stratagem. |

## Design notes

- **All art is generated in code** — inline SVG (concentric tick rings for Bard,
  flowing ribbons for Dancer) and a canvas ambient layer (drifting spores,
  rising embers). Nothing is a bitmap.
- **Palette discipline** — Bard is monochrome green, Dancer monochrome red, and
  the landing page is the only place the two meet.
- **Motion is opt-in** — every animation is behind
  `prefers-reduced-motion`, and the scroll reveals degrade to static content.
- **Numbers come from the guides** — potency values, timings and GCD targets on
  the pages are the real figures, not decoration.

## Viewing

Open `index.html` directly in a browser, or serve the folder:

```bash
python -m http.server 8080
# then visit http://127.0.0.1:8080/
```

## Layout

```
index.html              landing page (green/red diptych)
sites/
  bard-guide.html       Bard — The Resonance
  dancer-guide.html     Dancer — The Ember Waltz
  scholaranatomy/
    index.html          Scholar — Five Machines (interactive mechanics)
```

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
| [`sites/sch/`](sites/sch/) | Dark neutral | **Scholar — Five Machines.** Interactive isometric figures for Deployment Tactics, Aetherflow, Faerie Gauge, Summon Seraph, and Chain Stratagem. |
| [Bard — Five Machines](https://priestkos.github.io/ffxiv-bard-dancer-guides/brd/) | Dark neutral | **Bard — Five Machines.** Interactive isometric figures for five Bard mechanics. |
| [Dancer — Five Machines](https://priestkos.github.io/ffxiv-bard-dancer-guides/dnc/) | Dark neutral | **Dancer — Five Machines.** Interactive isometric figures for five Dancer mechanics. |
| [Samurai — Five Machines](https://priestkos.github.io/ffxiv-bard-dancer-guides/sam/) | Dark neutral | **Samurai — Five Machines.** Interactive isometric figures for five Samurai mechanics. |
| [Reaper — Five Machines](https://priestkos.github.io/ffxiv-bard-dancer-guides/rpr/) | Dark neutral | **Reaper — Five Machines.** Interactive isometric figures for five Reaper mechanics. |
| [Pictomancer — Five Machines](https://priestkos.github.io/ffxiv-bard-dancer-guides/pct/) | Dark neutral | **Pictomancer — Five Machines.** Interactive isometric figures for five Pictomancer mechanics. |

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

GitHub Pages serves a custom [`sites/404.html`](sites/404.html) for missing URLs.

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
  sch/
    index.html          Scholar — Five Machines (interactive mechanics)
  brd/
    index.html          Bard — Five Machines (interactive mechanics)
  dnc/
    index.html          Dancer — Five Machines (interactive mechanics)
  sam/
    index.html          Samurai — Five Machines (interactive mechanics)
  rpr/
    index.html          Reaper — Five Machines (interactive mechanics)
  pct/
    index.html          Pictomancer — Five Machines (interactive mechanics)
```

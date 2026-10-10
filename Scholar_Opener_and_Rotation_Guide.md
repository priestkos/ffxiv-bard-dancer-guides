# Scholar (SCH) — The Opener and Rotation, In Depth
### Final Fantasy XIV: Dawntrail · Level 100 · Patch 7.4 → 7.55

**Compiled:** 10 October 2026 · **Sources:** The Balance (SCH staff, patch 7.4), Icy Veins (patch 7.55, Zyrk), the official Lodestone job guide (last updated for patch 7.5), four video guides with full transcripts, and community discussion threads. Full citations in §17.

> **Patch note.** Scholar's *damage* rotation has not materially changed since 7.0 (Dawntrail launch). Every patch since has been a potency nudge or a radius increase. The 7.4 change (Biolysis 80 → 85) and the 7.3 change (Broil IV 310 → 320, most AoE radii 15y → 20y) are the only numbers that moved. 7.5 and 7.55 added **no** PvE Scholar action changes — 7.55's Scholar lines were PvP-side. Everything below is current.

---

## 1. Executive summary

Scholar is a barrier healer whose damage kit is deliberately thin: **one DoT, one filler nuke, one AoE, one oGCD nuke, one raid buff.** The opener is not hard. The *job* is hard, because the same resource (Aetherflow) pays for both your damage and your healing, and every stack you burn on damage is a bet that you won't need it for healing.

The rotation in one paragraph:

> Keep **Biolysis** on the target, fill every open GCD with **Broil IV**, use **Art of War II** at 2+ targets, press **Aetherflow** on cooldown and never let a stack go to waste, dump genuinely surplus stacks as **Energy Drain** — ideally inside 2-minute raid buffs — and land **Chain Stratagem** + **Baneful Impaction** in every 2-minute window, with **Dissipation** feeding three extra Energy Drains every 3 minutes.

The opener in one line:

> Precast Broil IV → potion → Biolysis + Dissipation → Broil → Chain Stratagem → Broil + Energy Drain ×3 → Broil + Aetherflow → Broil + Baneful Impaction → Broil + Energy Drain ×2 → Broil → **Biolysis (early refresh, last GCD under buffs)**.

The single most important number in this document:

> **3 Energy Drains = 300 potency. 1 Broil IV = 320 potency.** A single GCD heal costs you a 320-potency Broil *plus* ~900 MP. Therefore: **if spending a stack on Energy Drain later forces anyone — you or your co-healer — to cast one extra GCD heal, you have lost damage, not gained it.**

---

## 2. The damage baseline (verified potencies)

All values below are taken from the official Lodestone job guide rendered at level 100 (updated for patch 7.5) unless marked otherwise.

| Action | Lv | Type | Cast | Recast | Potency | Notes |
|:--|:--|:--|:--|:--|:--|:--|
| **Biolysis** | 72 | Spell, instant | — | 2.5s GCD | 85/tick, 30s = **850 total** | DoT, 1 target, 400 MP |
| **Broil IV** | 82 | Spell | 1.5s | 2.5s GCD | **320** | 400 MP. Raised from 310 by Tactician's Mastery in 7.3 |
| **Ruin II** | 38 | Spell, instant | — | 2.5s GCD | **220** | Movement only. −31% vs Broil IV |
| **Art of War II** | 82 | Spell, instant | — | 2.5s GCD | **180** per target, 5y radius | Centred on you, does not turn your character |
| **Energy Drain** | 45 | Ability | — | 1s | **100** | Costs 1 Aetherflow stack; +10 Faerie Gauge; absorbs part of damage dealt as HP |
| **Baneful Impaction** | 92 | Ability | — | 1s | **140/tick, 15s = 700 total** | AoE, 5y around target. Requires **Impact Imminent** from Chain Stratagem |
| **Chain Stratagem** | 66 | Ability | — | **120s** | — | Target takes critical hits **10% more often** for **20s**; grants Impact Imminent (30s) |

Derived rates, calculated rather than quoted:

| Metric | Value |
|:--|:--|
| Broil IV sustained damage rate | 320 / 2.5s = **128.0 potency/second** |
| Biolysis sustained rate | 850 / 30s = **28.3 potency/second** |
| Butterfly break-even vs a Broil GCD | **12s** (4 ticks = 340 ≥ 320); clearly ahead by 15s (5 ticks = 425) |
| GCDs covered by one Chain Stratagem window | 20s / 2.5s = **8 GCDs** |
| Total Aetherflow stacks per 3 minutes | 3 × Aetherflow + 3 × Dissipation = **12 stacks** (1,200 potency if all drained) |
| Value of a "six-ED" burst window | 600 potency ≈ **1.9 Broils** |
| MP restored per Aetherflow | 20% of max MP = **2,000 MP** at 10,000 max MP |

---

## 3. The resource economy — why the rotation is really about Aetherflow

### 3.1 Aetherflow itself

| Property | Value |
|:--|:--|
| Recast | **60s** |
| Grants | **3 stacks** + **20% of max MP** (2,000 MP) |
| Usable | In combat only |
| Spent on | Lustrate, Indomitability, Excogitation, Sacred Soil, **Energy Drain** |
| Gauge cap | 3 — **recasting it at 3 stacks discards the new ones** |

Aetherflow is the only recurring source of MP in the modern kit. Energy Drain no longer returns MP (that was removed in Endwalker and the MP moved onto Aetherflow itself), so Aetherflow is simultaneously your MP economy, your oGCD healing budget, *and* your only spare-damage resource. Every guide that reduces it to "free healing" is hiding the actual decision.

The operational rule is blunt: **press it on cooldown and enter every press with an empty gauge.** If the situation is "Aetherflow is about to come off cooldown and I still have stacks," spend them (Energy Drain if healthy, a heal if not) — that expenditure is free, because the stack is about to be deleted otherwise.

### 3.2 Energy Drain — the release valve, not the point

Energy Drain is 100 potency on the oGCD. Three of them are **300 potency — less than one Broil IV.** This matters, and at least one popular video guide gets it backwards (see §16).

The arithmetic that governs whether to drain:

| Spend the stack on… | Immediate value | Later consequence |
|:--|:--|:--|
| **Energy Drain** | +100 potency | If that stack was needed, you (or your co-healer) pay a **GCD heal: −320 potency and −900 MP** |
| **Healing oGCD** (Soil/Indom/Excog/Lustrate) | 400–800 potency of healing, no GCD cost | You cast Broil IV (320) instead of the GCD heal |

So the swing is asymmetric: **draining + a GCD heal = 100 − 320 = −220 potency and a lost GCD**; healing with the stack + casting Broil = +320 potency. The correct default, especially in progression, is:

> Use stacks for healing; drain only stacks you are *certain* you will not need before the next Aetherflow. Energy Drain is a reward for a solved timeline, not a default expectation.

Two structural notes that are easy to miss:

* Energy Drain **does not** cost MP — it *builds* Faerie Gauge (+10 per stack used). Three drains = 30 gauge = three ticks of Fey Union (300 potency/tick to a single target). The damage is small; the gauge is not nothing.
* Energy Drain heals **you** for a fraction of its damage ("absorbs a portion of damage dealt as HP"). Irrelevant in practice, but it is why the tooltip describes it defensively.

### 3.3 Dissipation — a damage cooldown with a healing-shaped cost

| Property | Value |
|:--|:--|
| Recast | **180s (3 minutes)** |
| Grants | **3 Aetherflow stacks** (full refill) |
| Also grants | **+20% healing magic potency** for the duration |
| Duration | **30s** |
| Cost | The faerie is removed: no Embrace, no Whispering Dawn / Fey Illumination / Fey Blessing / Aetherpact, Faerie Gauge does not fill, **Seraphism cannot be used** (and using Dissipation during Seraphism *ends* it) |
| Requirements | A faerie must be summoned; cannot be used while Seraph is out; the faerie returns automatically when the effect expires |

Modern Dissipation is a **damage cooldown first** and an emergency healing buff second. The +20% applies to *GCD healing* (Adloquium/Concitation/Physick etc.), which is the healing you are trying not to do, so the healing half is mostly a panic button (it is genuinely strong for a pre-planned Deployment-Tactics spread, worth roughly +20% on a 2,139-potency critical Adloquium spread — see §11.3).

**Ghosting warning:** faerie commands that have been issued but not yet executed (Whispering Dawn etc.) are **lost, with the cooldown consumed**, if you summon Seraph or press Dissipation at the wrong moment. Sequence fairy actions *before* Dissipation, not after.

**Why 3 minutes matters:** 180s means Dissipation fires roughly at 0:00, 3:00, 6:00 — i.e. it lines up with *every other* 2-minute burst window, not every one. That is exactly why the opener placement and the two-minute stack hand-off matter (§8).

---

## 4. Chain Stratagem and Baneful Impaction

Chain Stratagem is Scholar's raid contribution and the anchor of the entire damage plan.

| Property | Value |
|:--|:--|
| Recast | **120s** (aligns with the party's 2-minute burst) |
| Effect | Target takes critical hits **10% more often**, 20s |
| Stacking | **Additive** with your base crit chance and with other crit-*rate* buffs (Battle Litany etc.). It does **not** stack with a second Scholar's Chain Stratagem |
| Secondary effect | Grants **Impact Imminent** for 30s |
| Consumer | **Baneful Impaction** — 140 potency/tick AoE DoT, 15s (700 total), 5y around the target; consumes Impact Imminent |

Practical consequences:

1. **Chain changes when your own burst happens.** Because Baneful Impaction can only be used while Impact Imminent is up, and because you want it inside raid buffs, your own damage peak is now defined by Chain — not by a separate cooldown.
2. **Delay is usually wrong.** Use it in the opener, then on cooldown, unless your group is deliberately holding the 2-minute window (phase transition, kill time, a boss about to become untargetable). Two minutes of held Chain is a much bigger loss than any local gain.
3. **It is worth using on trash.** The AoE originates from the target, so tag a *central* mob and follow with Baneful Impaction for a large multi-target DoT. This is one of the few places Scholar "gains" a cooldown that other healers do not have.
4. **Two Scholars**: stacking between two Chain Stratagems is not stated on the Lodestone entry (unverified). Coordinate timing with your co-healer.

---

## 5. DoT theory — Biolysis, clipping, and the "early refresh"

Biolysis is 85 potency every 3 seconds for 30 seconds (850 total, 28.3 potency/second, 400 MP, instant cast). Compared with a Broil IV GCD (320 potency, 128 potency/second) it is *only worth casting* if it will actually tick:

| Time the DoT will remain on the boss | Ticks | Potency | vs one Broil IV (320) |
|:--|:--|:--|:--|
| 9s | 3 | 255 | −65 |
| **12s** | 4 | 340 | **+20 (break-even)** |
| 15s | 5 | 425 | +105 |
| 21s | 7 | 595 | +275 |
| 30s (full) | 10 | 850 | +530 |

Thresholds used in practice:

* **Single target:** maintain Biolysis as long as it will be on the boss for **≥ 12s**. If the boss is about to die or become untargetable inside that window, don't cast it.
* Refresh **late, not early** — normally at 0–3 seconds remaining. Early refresh is a DPS *loss* unless it buys you something specific (movement, or the burst-window alignment below).
* **Multi-target:** the break-even scales with how many targets your AoE filler would be hitting. 2 targets → 15s; 3 targets → 21s; 4 targets → 27s; **5+ targets → skip Biolysis entirely and spam Art of War II.** In dungeon pulls, apply Biolysis to mobs one by one *while the tank is running* (instant cast, free uptime).

### The "early refresh" (DoT clip) — and why the opener does it

Since raid buffs were standardised to at least 20 seconds, **clipping Biolysis on the final GCD of the burst window is a gain.** The reason is alignment, not raw potency: refreshing at the *end* of the buffs makes each subsequent natural refresh (every 30s) drift toward the end of future buff windows rather than out into dead air.

Payback period (Icy Veins, 7.55):

* With **one additional party raid buff** beyond Chain Stratagem: the early refresh is a net gain after **~2 minutes of uptime**.
* With **no other raid buffs at all**: **~4 minutes**.
* If downtime resets your DoT alignment before that threshold, don't bother — but that is rare.

**The GCD breakpoint is real.** At a 2.48s GCD you can fit eight Broil IVs and still catch Chain Stratagem with the refreshed Biolysis. The Balance's gear page adds a sharper caveat: **at 2.49–2.50 GCD, Biolysis cast *after* your 6th Energy Drain will not land inside Chain Stratagem — put the DoT on the same GCD as the 6th Energy Drain instead.** That is a one-GCD difference deciding whether the clip is a gain or a waste.

**Instant-cast utility:** Biolysis is instant, so a natural refresh is a free movement GCD, and an *unnatural* refresh can be used to double-weave two oGCDs. Do not manufacture extra refreshes just to move — slidecast or Swiftcast instead.

---

## 6. Weaving, the GCD model, and the 1.5s cast

Scholar's model in Dawntrail is unusual among casters and it changes how the opener is built:

| GCD type | Cast time | Weave capacity |
|:--|:--|:--|
| **Broil IV** | **1.5s** (recast 2.5s) | **1 oGCD with no clip**; a second clips slightly |
| Instant GCDs (Biolysis, Art of War II, Ruin II) | — | **2 oGCDs with no clip** |

Because Broil's cast is only 1.5s, the window *after* the cast and the slidecast window *before* the end stack up: you get roughly a second of free movement after every Broil, plus ~0.5s of slidecast. That is why modern advice is to **avoid Ruin II wherever possible** — with a 1.5s cast you can usually slidecast to the destination, and Ruin II costs you 100 potency (31% of a Broil) every time.

The practical opener consequence: **single-weave everything.** One oGCD after each Broil. Double-weaving belongs on instant GCDs (Biolysis, Art of War) only.

Slidecast window is ping-dependent. A common learning trick: put an emote (or any instant action) on your bar during the cast — when it lights up, you are inside the window and can move without cancelling.

---

## 7. The Level 100 opener

### 7.1 Pre-pull

| Time | Action | Why |
|:--|:--|:--|
| **−1.5s** | Precast **Broil IV** | Its 1.5s cast completes exactly as the boss becomes targetable — the standard caster pre-pull |
| **0.0s** | **Grade 4 Gemdraught of Mind** | Weave the potion immediately after the precast, *before* the first GCD |

The potion does **not queue** — you must mash the key, or it will not fire. Placing it here means it buffs the opening Biolysis *and* the early refresh at the end of the window, so it covers the full burst. (If the potion and the burst are misaligned by a phase change or an unusual pull timer, the potion is the thing people move; the Chain Stratagem is not.)

### 7.2 The timeline

The opener is **11 GCDs** long (~25s) and is identical in content across every current source; the only genuine disagreement is whether Chain Stratagem lands on the 2nd or 3rd GCD (§7.5). This table follows The Balance's published level-100 diagram, which places Chain on **GCD 3** and shows Dissipation in the first slot.

| GCD | GCD action | oGCD weave | Rationale |
|:--|:--|:--|:--|
| pre | *Broil IV (precast)* | — | Damage on the pull; potion woven after |
| **1** | **Biolysis** | **Dissipation** *(or Aetherflow)* | DoT up immediately and under the potion; Dissipation's stacks arrive as the burst begins |
| **2** | Broil IV | — | Free GCD; Broil's 1.5s cast makes this the natural single-weave slot |
| **3** | Broil IV | **Chain Stratagem** | Opens the party's 2-minute window and your own DoT/channel alignment; grants Impact Imminent |
| **4** | Broil IV | **Energy Drain** | Drains begin inside Chain |
| **5** | Broil IV | **Energy Drain** | |
| **6** | Broil IV | **Energy Drain** | Third and last stack from the first set |
| **7** | Broil IV | **Aetherflow** *(or Dissipation)* | Refills to 3 stacks — never hit Aetherflow with stacks left |
| **8** | Broil IV | **Baneful Impaction** | 700 potency inside Chain Stratagem; single-wheel it, never late |
| **9** | Broil IV | **Energy Drain** | New stacks, still inside buffs |
| **10** | Broil IV | **Energy Drain** | |
| **11** | **Biolysis** (early refresh) | **Energy Drain** | The early refresh lands as the **last GCD under raid buffs** — this is the whole point of the opener's shape |

Aetherflow and Dissipation are the **only** swappable elements. If Aetherflow goes first and Dissipation second, the order shown on GCD 1 / GCD 7 flips and nothing else changes.

### 7.3 Which order: Aetherflow-first or Dissipation-first?

Both are correct; they answer different questions.

**Aetherflow-first — the "standard" / progression opener**

* Aetherflow on GCD 1, Dissipation on GCD 7.
* Most flexible: easiest to *drop* Energy Drains and to drop Dissipation entirely if the fight's opening damage forces GCD healing.
* This is what you use while learning a fight — and Icy Veins explicitly recommends holding both Aetherflow and Dissipation during early progression and working them in later.

**Dissipation-first — the optimised default**

* Dissipation on GCD 1, Aetherflow on GCD 7.
* Advantages (The Balance's opener notes):
  1. The faerie is gone *earlier*, so she is back ~15s sooner — and her downtime happens before the first real healing check.
  2. The 2,000 MP from Aetherflow arrives **later**, so less of it is wasted to an already-full MP bar.
  3. It lines Aetherflow up so that the 2-minute window can hold **six Energy Drains** (three carried from the odd minute + three fresh) without delaying anything.
  4. With raid buffs now 20s long, the extra stacks fit inside buffs more consistently.
* Drawback: **you risk losing one Aetherflow use** over the fight or phase, and the stack timings shift, which changes your healing plan. Both problems are shared by any rotation that does six-ED windows every two minutes.

Rinon's framing of the trade-off is the cleanest version: *Dissipation-first is standard now because buffs are 20s and you want as many Energy Drains inside them as possible; Aetherflow-first exists for fights where you'd be cutting it fine on getting three charges spent before the boss dies.*

### 7.4 What to cut in progression

The opener above is the dummy opener. In real fights:

* **Skip one, two, or all three of the trailing Energy Drains** if you need stacks for healing in the first minute. Cutting from the *end* is correct — it preserves the shape and the alignment.
* **Hold at least one stack** until you trust the fight; the Balance and every video guide say the same thing in different words.
* If you don't feel safe removing the faerie for 30s (a heavy healing opening), **skip Dissipation entirely** and treat the lost damage as the cost of safety. It is roughly 300 potency — less than one Broil.

### 7.5 The one genuine disagreement: Chain Stratagem on GCD 2 or 3?

| Source | Patch | Chain Stratagem lands on | Burst shape |
|:--|:--|:--|:--|
| The Balance — Openers (diagram) | 7.4 | **GCD 3** (two Broils after Biolysis) | 11 GCDs, refresh on GCD 11 |
| Icy Veins — DPS Rotation (text) | 7.55 | **GCD 2** (one Broil after Biolysis) | 8 Broils from GCD 3, refresh on the final GCD |
| Icy Veins — Job Changes (text) | 7.3 | **GCD 3** | same as Balance |

Both produce the same outcome — Chain Stratagem covering the eight GCDs leading into the early Biolysis refresh — and the difference is one GCD of latency on the buff. Practical guidance: **align Chain with the party's buff timer**, which on most NA/EU groups means the window opens around X:06–X:07 after the pull; if your group's buffs land one GCD later than the Balance diagram assumes, you are a GCD-2 Chain group, and if they land where the diagram places them, you are a GCD-3 group. Do not agonise: the difference is a fraction of a Broil, and being one GCD *early* is strictly safer than being late, because Chain's 30-second Impact Imminent window forgives the Baneful Impaction placement.

---

## 8. After the opener: the 1 / 2 / 3-minute cadence

Once the opener ends, Scholar runs an extremely regular loop. The rotation is really a **60-second resource cycle inside a 120-second buff cycle, with a 180-second wildcard**.

### 8.1 The steady state

```
0:00  ── Aetherflow (3 stacks) ──────────────── spend over the next 60s
0:60  ── Aetherflow (3 stacks) ──────────────── spend over the next 60s
2:00  ── Aetherflow + Chain Stratagem + Baneful Impaction  ← the real burst
3:00  ── Dissipation (3 stacks) + Aetherflow
        ... and repeat: Aetherflow every minute, Chain every 2, Dissipation every 3
```

Rules of thumb:

1. **Biolysis every 30s**, refreshed with 0–3s left, never dropped.
2. **Broil IV in every other GCD.** This is >90% of your GCDs outside healing.
3. **Aetherflow on cooldown**, gauge emptied first.
4. **Chain Stratagem on cooldown** (2 minutes) unless the group is holding.
5. **Baneful Impaction immediately after every Chain Stratagem**, inside raid buffs, on a central target in AoE.
6. **Energy Drain only where it is provably free** — and prefer the 2-minute windows so the drains sit under buffs.
7. **Lucid Dreaming** somewhere around the end of the opener, then on cooldown — the practical trigger is "below ~8,000–9,000 MP and Lucid is up." Lucid restores 3,850 MP over 21s.

### 8.2 The six-Energy-Drain buff window

Because Aetherflow is 60s and buffs are 120s, the *odd* minute hands you a decision: spend those three stacks now, or carry them into the 2-minute window to make a six-ED window (600 potency inside buffs)?

* Carrying them costs you nothing **if** you would not have needed them for healing and **if** you can still press Aetherflow on time at 2:00.
* The Balance's note is explicit: with a Dissipation-first opener, Aetherflow is *already* aligned so that six-ED windows at two minutes happen naturally. With an Aetherflow-first opener you can achieve the same thing by simply delaying the 2-minute Aetherflow slightly.
* The risk is the standard one: **you may lose an Aetherflow cast** over the encounter, and your stacks arrive later than your healing plan assumed.

### 8.3 Dissipation's 3-minute grid

Dissipation (180s) does not land in every 2-minute window. That gives you the freedom to slide it:

* **0:00 / 3:00 / 6:00** — off cooldown, maximum total stacks, aligns with every other burst.
* **0:00 / 4:00 / 7:00** — the shift used when you want Dissipation to coincide with a Recitation or a GCD-healing phase (the +20% healing buff) rather than with burst. This loses *no* usage in a fight of that length.

The planning question is always: *which phases need my faerie, and which phases need three more Energy Drains?* Note that Dissipation **cannot overlap Seraphism** — and they are both repositories of "big healing for a hard phase." Decide in advance which one covers each heavy window, because you cannot layer them.

---

## 9. Priority systems

### 9.1 Single target (Icy Veins, 7.55)

1. Maintain **Biolysis** as long as it will be on the boss for **≥ 12 seconds**.
2. Use **Chain Stratagem** on cooldown after the opener, unless the group is holding buffs for a mechanic or kill time.
3. Use **Baneful Impaction** under raid buffs.
4. Use **Broil IV** whenever you have time to cast and don't need a GCD heal (>90% of GCDs).
5. Use **Ruin II** when movement prevents Broil IV and you cannot/‌will not Swiftcast. Avoid by pre-positioning.
6. Use **Energy Drain** when the stacks are not needed for healing; prefer 2-minute windows.

### 9.2 Multi-target

1. **Art of War II** is a gain over Broil IV at **2+ targets** (360+ vs 320).
2. 2 targets: Biolysis on anything living **≥ 15s**.
3. 3 targets: **≥ 21s**. 4 targets: **≥ 27s**. **5+ targets: skip the DoT.**
4. Dungeon pulls: apply Biolysis to mobs individually *while following the tank*, then settle into Art of War II.
5. Energy Drain is still usable; aim it at the highest-health target so the damage isn't wasted on a corpse.
6. Baneful Impaction is a **massive** AoE gain — Chain Stratagem on the healthiest mob, then Baneful the group (unless they die inside the 15s).

### 9.3 Weaving quick reference

| After… | Weave safely |
|:--|:--|
| Broil IV (1.5s cast) | **1** oGCD (2 clips slightly) |
| Biolysis / Art of War II / Ruin II | **2** oGCDs |
| Adloquium / Concitation (2s cast) | ~0 — clips; use prepull or in downtime |

Because shields now begin applying *during* the slidecast window rather than at cast completion, **Adloquium → Deployment Tactics no longer ghosts** — but it still clips your next GCD, so keep it for prepull/downtime unless you are deliberately cheesing a mechanic.

---

## 10. Maintaining uptime (movement)

Ranked by cost, cheapest first:

1. **Slidecasting** — ~0.5s before the cast ends, ping-dependent. Combined with the ~1s gap after each 1.5s Broil cast, this is most of what you need.
2. **Natural Biolysis refreshes** — every 30s you get a free instant GCD. Plan mechanics around it; also usable for a double weave when you need two oGCDs in a row (e.g. Whispering Dawn + Recitation).
3. **Pre-positioning** — the actual solution; mechanics are scripted, you know where you must be.
4. **Swiftcast** (40s with the level-94 trait) — a wholly free GCD of movement, but it is also your raise button. In progression, price it accordingly.
5. **Seraphism** — while active, Manifestation/Accession are instant, which frees movement. The Balance's caveat stands: *casting a GCD heal is not better than doing nothing*, so this is only a movement gain if you were going to GCD heal anyway.
6. **Ruin II** — last resort; 220 vs 320. Better than dropping a cast.
7. **Art of War II on a single target** — a niche Scholar trick. It is instant and **does not turn your character**, so during gaze/monitor mechanics (e.g. an Omega-protocol-style "don't face the boss" check) it lets you hold an exact facing while still dealing damage. You lose damage versus a well-timed Broil, but far less than doing nothing.

**Auto-attacks:** healers must manually re-enable auto-attack after moving back into melee range. Scholar's autos are the best of the four healers (~100–150 per swing). The gain is trivial; the habit is not.

---

## 11. The healing layer (rotation and mitigation cannot be separated)

### 11.1 The healing priority ladder

Scholar has the most stratified healing priority of any healer. Think in terms of **what each option costs you in damage**:

| Tier | Examples | Damage cost |
|:--|:--|:--|
| **Free oGCD** (faerie) | Whispering Dawn, Fey Blessing, Fey Illumination, Summon Seraph + Consolation, Aetherpact, Embrace (passive), Protraction | **0 potency** |
| **Aetherflow oGCD** | Sacred Soil, Indomitability, Excogitation, Lustrate | **100 potency each** (one Energy Drain) |
| **GCD healing** | Adloquium, Concitation, Physick, Manifestation, Accession, Emergency Tactics | **320 potency each** (one Broil IV) **plus MP** |

The working order: **Free → Aetherflow → GCD**, with the standing caveat that a lower tier is sometimes correct — when it saves a cooldown you need later, or when a Sacred Soil or a Deployed Adloquium makes a mechanic surviveable rather than merely cheaper.

Within the Aetherflow tier, community consensus orders it: **Sacred Soil > Excogitation > Indomitability > Lustrate > Energy Drain**. Sacred Soil is listed as the highest-value Aetherflow heal in *both* single-target and AoE contexts because 10% mitigation + a 100-potency regen (six ticks over 15s from a 30s cooldown) is worth more than Lustrate's raw 600.

### 11.2 Ability-level notes that change how you play the rotation

* **Sacred Soil** (30s recast, 15s, 15y, 1 stack): mitigation **and** regen, *not* a barrier. Barrier HP and percentage mitigation stack differently against a hit — do not plan a raidwide as though Soil contributed shield HP. Below level 78 it has no regen; don't use it for healing value in synced-down content.
* **Excogitation** (45s, 800 potency, triggers below 50% or on expiry): your default single-target Aetherflow heal; does **not** prevent a one-shot from above 50%. Place it on a tank before a buster or on a freshly raised player (it pops instantly below 50%).
* **Indomitability** (30s, 400 potency, 20y in 7.3+): the pairing of choice with **Recitation** for burst AoE healing.
* **Lustrate** (600 potency, no real cooldown, 1 stack): the "spend leftover stacks in downtime so Aetherflow doesn't drift" button, and the emergency spot heal.
* **Recitation** (60s, 15s duration, one charge): removes the cost of Adloquium / Concitation / Indomitability / Excogitation **and** guarantees a crit. Preferred uses in order: **Indomitability** (raid) → **Excogitation** (tank) → **Adloquium + Deployment Tactics** (progression safety / surprising raidwides) → *never* Concitation/Succor. It still generates Faerie Gauge even though it costs nothing. Do **not** use it prepull unless it will not be needed inside ~45s; if you need a big shield on the pull, fish for a crit Adloquium instead.
* **Deployment Tactics** (90s after the level-88 trait, so it naturally lines up with Recitation): spreads **Galvanize only — never Catalyze**. A Recitation-critical Adloquium gives the target both shields (~2,139 total potency) but the party receives only the Galvanize portion. Still excellent; just smaller than the folklore. Also: it does not copy other players' shields, and the copied shield keeps the original's remaining duration.
* **Protraction** (60s, 10s): +10% max HP, heals for the amount added, +10% healing received. Use **before** Adloquium (bigger shield to deploy) or **before** Excogitation/Fey Union — those **snapshot** the healing-received buff at cast time. Using it *after* Excogitation does nothing for a heal that triggers later.
* **Expedient** (120s, 30y): 20s of 10% mitigation plus 10s of Sprint-equivalent movement. In dungeons it pulls your tank faster; in raids it is a movement answer no other healer can replicate.
* **Seraph / Consolation** (120s, 22s; Consolation 2 charges, 30s recast): Consolation is half heal, half shield, and its shield stacks with yours (but not with itself). Best used when raidwides repeat inside a short interval — one near the start of the window and one near the end. **Launching Seraph discards any pending fairy command** (ghosting). Whispering Dawn and Fey Illumination remain usable while Seraph is out but waste her time; use them before summoning or after she leaves.
* **Seraphism** (180s, 20s): a 100-potency party regen at 50y — effectively un-outrangeable on a standard arena — with a hidden 5s duration, so each member takes **7–8 ticks (700–800 potency)**. It also converts Adloquium → **Manifestation** (360 heal + 180% shield, instant) and Concitation → **Accession** (240 + 180%, instant), and **resets Emergency Tactics with a 1-second recast** for the duration — Scholar's only way to brute-force a heal-to-full check quickly. Lodestone lists **"Effect cannot be stacked with Dissipation"** (the two cannot be active together) and requires a faerie or Seraph summoned, in combat. *Interaction with Recitation is not stated on the Lodestone entry; an earlier draft claimed it was blocked and that claim is unverified.*
* **Emergency Tactics** (15s, becomes 1s during Seraphism): converts the barriers on your next Adloquium/Concitation into raw healing. Use in downtime to top the party; during uptime only if *all* of: a heal-to-full mechanic demands it, you have no oGCD tools, your co-healer has none either, and it is cheaper for you to cast it than for them.
* **Physick** (450): only when out of MP with no oGCDs, or when you need a faster single-target heal than Adloquium's 2s cast.
* **Fairy placement**: Place is a **free action — it does not consume a weave slot** and can be pressed mid-cast without clipping, which is why macroing it is acceptable here (unlike combat macros generally). Put her mid-arena for raidwides; the fairy's heals originate from *her*, not you. Pet potency is real: her throughput is worth ~0.89× player potency in a party (role bonus applied), ~0.93× solo.
* **Aetherpact / Fey Union** (300/tick, 10 gauge per tick): your strongest sustained single-target heal, and the payoff for draining stacks (each drain = 10 gauge). She will *not* move or Embrace while tethered; any other fairy action cancels it.

### 11.3 The actual burst-healing combo people ask about

> **Protraction → (fish for, or Recitation) critical Adloquium → Deployment Tactics**

Non-crit Adloquium = 300 heal + 540 Galvanize = 840. A **crit** Adloquium ≈ (300 + 540 + 540) × 1.55 ≈ **2,139** — 3.8× a Concitation (560). Deployment spreads the Galvanize half to the party. Adding Dissipation's +20% on top of the cast is legitimate, if you can spare the faerie.

---

## 12. Edge cases, traps, and contested advice

1. **The six-ED trap.** The famous "dump 6 Energy Drains in burst" line is an optimisation for a *solved* timeline. If it forces your co-healer to spend a GCD heal you could have covered with a stack, the party loses damage. Every experienced source says the same thing in different words: ED is a reward for reducing GCD healing, never a goal in itself.
2. **Aetherflow overcap.** Pressing Aetherflow with 3 stacks live deletes the new stacks. Also: pressing it during downtime does nothing useful (it requires combat) — spend leftover stacks *before* the downtime instead.
3. **Stack drift compounds.** Aetherflow on cooldown is not a stylistic preference; every second of delay cascades through the fight's healing plan.
4. **Don't drain into a GCD heal.** The −220 potency swing described in §3.2 is the most common DPS leak in the job.
5. **Dissipation vs Seraphism.** They cannot be active together (Lodestone: "cannot be stacked with Dissipation"). Whether using Dissipation mid-Seraphism ends it is *not* stated on the Lodestone entry and is unverified.
6. **Ghosting.** Seraph and Dissipation both discard queued fairy actions. Double-weaving fairy commands is unreliable even now that response times improved — single-weave them.
7. **Shield overwrite rules with a Sage co-healer.** Galvanize is overwritten by Eukrasian Diagnosis; Galvanize and Eukrasian Prognosis overwrite each other (newest wins). **Catalyze neither overwrites nor is overwritten by any other shield.** Plan who shields what, or you are paying MP for a shield that is deleted on landing.
8. **Sacred Soil is not a shield.** Covered above, but it is the single most repeated correction in current guides.
9. **Deployment spreads Galvanize, not Catalyze.** Covered above.
10. **Two Scholars:** the Lodestone entry does not address stacking between two Chain Stratagems. Treat as unverified; coordinate with your co-healer to be safe.
11. **Ruin II creep.** In progression, Ruin II is genuinely useful; the moment you know the fight, every Ruin II is a 100-potency leak. Track it.
12. **Potion discipline.** The Gemdraught does not queue. It must be mashed, and it must precede the first GCD if you want it on both Biolysis casts.
13. **Recitation prepull.** Tempting for a pull shield; usually wrong. If you need a shield *now* and Recitation is needed inside 45s, fish for the crit instead.
14. **Misinformation in circulation.** A widely-shared "7.x healer changes" proposal thread describes Dissipation at 120s granting Ruin II charges and Energy Drain losing its Aetherflow cost, and other guides describe Dissipation as "sacrificing the fairy" permanently, or as restoring a flat 2,000 MP. **Live values:** Dissipation is **180s**, the faerie returns automatically, and the MP comes from Aetherflow's 20%-of-max restore. Also note that some 7.0-era content still quotes **Broil IV at 310** — the level-94 trait raised it to **320** in 7.3.

---

## 13. Gear, stats, and consumables

**Stat priority (The Balance, SCH):** Weapon Damage > Mind > **Crit** > DH = Det.

* At level 100, **item level almost always beats optimal sub-stats** — take the higher-ilvl piece if it has Mind.
* **Crit** is the offensive priority. Crit rate feeds Chain Stratagem windows and, indirectly, Adloquium's Catalyze.
* **Direct Hit** does nothing for healing but is otherwise the best damage filler stat; healers never find it natively, which is why it is melded.
* **Determination** also increases healing output — the usual pick if you are worried about throughput in early progression.
* **Piety**: only worth what your encounter's MP demands (you have Lucid Dreaming + Aetherflow's 2,000 MP per minute). Excess Piety beyond your MP floor is a dead stat.
* **Spell Speed**: Scholar cares about *GCD tier*, not comfort. Two data points from the current Balance sheets:
  * 2.48 GCD is the breakpoint at which you can fit 8 Broils and still catch Chain with the early-refresh Biolysis.
  * At a 2.49–2.50 GCD, use the *Biolysis on the same GCD as your 6th Energy Drain* variant instead — otherwise the refresh misses Chain.
  * 7.55's sets run 2.40 (and 2.31 sims higher but loses crit/DH, so 2.40 gives luckier runs); no 2.50 sets exist this tier because of Piety.
* **Frame alignment**: your true GCD is quantised to your frame rate, so a "2.50" set may behave like 2.505 on a low-FPS machine. Tools like ReAction sync the GCD to frames; `gcdcalc.fly.dev` will measure your *actual* GCD from an FFLogs pull. Feed it two or three logs and ignore outliers.
* **Weapons (7.55 context):** the completed relic **Phantom Codex Occultum** is i795; Savage weapons are i795 / augmented tome i790-class. Tome buy order per the Balance: Chest > Wrist > Ring > Ring.
* **Food:** Caramel Popcorn (Crit/Det, +91/+151) is the standard "max damage" pairing; Popoto Potage (Crit/Speed) for speed-tuned sets — pick from your actual gearset rather than by main stat.
* **Potion: Grade 4 Gemdraught of Mind** (current Dawntrail Mind medicine, introduced with 7.4). Older Grade 1/Grade 2 Tincture of Mind references are stale.

### Quick-reference card

```
PRE-PULL   -1.5s Broil IV  ·  0.0s Potion (mash it)
GCD 1   Biolysis      + Dissipation / Aetherflow
GCD 2   Broil IV      (+ Chain Stratagem — 2nd or 3rd GCD, per group)
GCD 3   Broil IV      + Energy Drain
GCD 8   Broil IV      + Aetherflow / Dissipation
GCD 9   Broil IV      + Baneful Impaction
GCD 11  Biolysis      (early refresh = last GCD under buffs)

THEN       Aetherflow @ 0:60 / 1:60 / 2:60 ...
           Chain Stratagem + Baneful @ 2:00 / 4:00 / 6:00 ...
           Dissipation @ 3:00 / 6:00 (or 4:00 / 7:00)
           Biolysis every 30s · Broil IV everything else
           Energy Drain only when provably surplus
```

### Level-sync floors (for roulette content)

| Lv | Unlocks | Effect on the plan |
|:--|:--|:--|
| 45 | Aetherflow, Lustrate, Energy Drain | The kit's core exists |
| 50 / 52 | Sacred Soil / Indomitability | Aetherflow healing tier complete |
| 58 | Emergency Tactics | Shield→heal conversion |
| 60 | **Dissipation** | Damage cooldown arrives |
| 62 / 66 | Excogitation / **Chain Stratagem** | Single-target heal + the raid buff |
| 70 / 74 / 76 | Aetherpact / Recitation / Fey Blessing | Gauge economy + free crits |
| 78 | **Enhanced Sacred Soil** | Soil gains its regen — before this it is mitigation only |
| 80 | Summon Seraph / Consolation | Second shielding package |
| 85 / 88 | Enhanced Healing Magic / DT 9s→90s | Big Adlo/Succor barriers |
| 90 / 92 | Expedient / **Baneful Impaction** | Raid movement + the DoT |
| 94 / 96 / 98 | Swiftcast 40s, Broil 320, Concitation / Recitation 60s | Current numbers |
| 100 | **Seraphism** | The capstone |

Below 78 Sacred Soil is mitigation only; below 92 there is no Baneful Impaction; below 100 no Seraphism, and Dissipation/Seraph conflict rules change how you plan phases.

---

## 14. Patch history 7.0 → 7.5 (what actually changed)

| Patch | Scholar change |
|:--|:--|
| **7.0** | Chain Stratagem duration 15s → **20s**, and gains **Impact Imminent** → **Baneful Impaction** (Lv92). Broil IV 295 → 310. Biolysis 70 → 75. **Recitation 90s → 60s.** New: Concitation (Lv94), Seraphism (Lv100, with Manifestation/Accession), traits Enhanced Chain Stratagem (92), Enhanced Swiftcast (94, 60s→40s), Tactician's Mastery (94), Succor Mastery (96), Enhanced Recitation (98) |
| **7.1** | Adloquium/Succor/Concitation/Manifestation/Accession MP 1,000 → **900**. Embrace and Seraphic Veil cure potency 150 → **180** |
| **7.2** | Biolysis DoT 75 → **80** |
| **7.3** | Broil IV potency (via Tactician's Mastery) 310 → **320**. Succor, Concitation, Accession, Whispering Dawn, Angel's Whisper, Indomitability radii **15y → 20y**. Fey Blessing visuals fixed |
| **7.4** | Biolysis DoT 80 → **85**. Grade 4 Gemdraught of Mind introduced |
| **7.5 / 7.55** | **No PvE Scholar action changes** (Scholar lines were PvP-side). 7.55 completes the Phantom relic weapon line (i795) |

The net effect across the expansion: Scholar's *damage* rotation has been untouched since launch. What changed is that raid buffs became 20 seconds, which is what turned the early Biolysis refresh from a niche optimisation into standard practice.

---

## 15. Practice and verification

1. **Dummy opener drills.** Run the 11-GCD opener on a striking dummy until the weave order is automatic; the only thing that changes in a real fight is which Energy Drains you delete.
2. **Practice the two variants** (Aetherflow-first, Dissipation-first) until you can switch mid-fight without thinking.
3. **Audit with FFLogs / XIVAnalysis.** Useful checks:
   * Aetherflow casts per fight, and whether any press found stacks still in the gauge.
   * Chain Stratagem uptime and Baneful Impaction count (should match Chain casts 1:1).
   * Biolysis uptime and number of early/unnecessary refreshes.
   * Ruin II count vs total GCDs (any creep is visible immediately).
   * Energy Drains inside buff windows vs outside.
4. **Track your real GCD** with `gcdcalc.fly.dev` from a log before committing to a GCD-tier gearset — and cross-check the 2.47/2.48 breakpoint against whether your early refresh actually lands under Chain.
5. **The Balance Discord** hosts the up-to-date gear sheets and the SCH question channels; the site pages lag the Discord by weeks, and the *openers page* in particular has carried a 7.4 stamp since December 2025.

---

## 16. Source conflicts, corrections, and open questions

Surfaced deliberately rather than smoothed over:

| Issue | Detail |
|:--|:--|
| **Chain Stratagem GCD 2 vs GCD 3** | Icy Veins' 7.55 text places it on the 2nd GCD; The Balance's 7.4 diagram and Icy Veins' own 7.3 page place it on the 3rd. Both produce an 8-GCD window ending in the early refresh. Resolve by party buff timing. |
| **Broil IV 310 vs 320** | Pages written before 7.3 still say 310 (Icy Veins' DPS page still does, while its own job-changes page says 320). Official value at level 100 is **320**. |
| **"3 Energy Drains are slightly stronger than one Broil"** | A claim made in Rinon's level-100 guide. Arithmetically the opposite: 3 × 100 = **300 potency vs Broil IV's 320**. The conclusion he draws (ED is a small gain; don't overvalue it) is correct; the comparison is not. |
| **Dissipation's cooldown** | A widely-read community rework proposal lists Dissipation at 120s with Ruin II charges. That was a *suggestion*, not a patch. Live: **180s**. |
| **"Dissipation sacrifices the fairy"** | She returns automatically after 30s. The real cost is 30 seconds without fairy abilities, gauge generation, and Seraphism. |
| **Consolation radius** | Community guides say 20y; the Lodestone pet-action table lists 30y for the pet-order version. Position the fairy centrally and it does not matter. |
| **Succor barrier 160% vs 180%** | The level-85 trait brings Adloquium to 180%; Succor stays at 160% and its level-96 upgrade Concitation is 180%. Guides that quote "180% Succor" are conflating the two. |
| **Potion grade** | 7.3-era pages quote Grade 1 Gemdraught; the current item is **Grade 4 Gemdraught of Mind** (7.4+). Any "Grade 2 Tincture of Mind" reference is an older expansion. |

**Open questions worth testing yourself on a dummy or in a log review:**

* Does the Dissipation-first opener actually net you an extra Aetherflow use in your group's typical kill time, or does it quietly cost one?
* At your GCD tier and ping, does the GCD-11 Biolysis really land inside the last tick of Chain Stratagem?
* In your static, who owns which mitigation for each raidwide — and does that plan leave you a genuinely free Energy Drain window at 2:00, or only a theoretical one?

---

## 17. Bibliography

**Community guides (primary)**

1. The Balance — *Scholar* hub (patch 7.4, updated 27 Dec 2025). https://www.thebalanceffxiv.com/jobs/healers/scholar/
2. The Balance — *Openers* (patch 7.4, last updated 27 Dec 2025), including the level-100 opener diagram *"Scholar early dot refresh opener"* and the Dissipation-first / early-refresh notes. https://www.thebalanceffxiv.com/jobs/healers/scholar/openers/
3. The Balance — *Basic Guide* (patch 7.4), healing priority, movement options, gauges, stat priority. https://www.thebalanceffxiv.com/jobs/healers/scholar/basic-guide
4. The Balance — *Skills Overview* (patch 7.4), full action-by-action potency and usage commentary. https://www.thebalanceffxiv.com/jobs/healers/scholar/skills-overview
5. The Balance — *Frequent Questions* (patch 7.4): fairy nameplate, Place macro, Chain-window FFLogs pin, shield application timing, pet potency, Ruin II policy, Consolation keybind note. https://www.thebalanceffxiv.com/jobs/healers/scholar/faq
6. The Balance — *Recent Changes* (patch history). https://www.thebalanceffxiv.com/jobs/healers/scholar/job-changes
7. The Balance — *Best in Slot* (patch 7.55, updated 9 Aug 2026): GCD frame-alignment note, the 2.47/2.49 DoT-refresh breakpoint warning, 2.40/2.31 set discussion, tome buy order, i795 relic. https://www.thebalanceffxiv.com/jobs/healers/scholar/best-in-slot
8. Icy Veins — *Scholar DPS Rotation for Healers* (patch 7.55, Zyrk, last updated 28 Jul 2026): opener text, single-target and multi-target priority lists, uptime tools. https://www.icy-veins.com/ffxiv/scholar-dps-rotation-for-healers
9. Icy Veins — *Scholar Healing Rotation, Ability Priority, and Cooldowns* (7.55): healing ladder, free/Aetherflow/GCD tiers, Seraphism notes. https://www.icy-veins.com/ffxiv/scholar-pve-healing-rotation-ability-priority
10. Icy Veins — *Scholar Job Changes and Updates* (7.55): per-patch tables 7.0 → 7.4, new actions and traits. https://www.icy-veins.com/ffxiv/scholar-job-changes-updates
11. Icy Veins — *Leveling Rotations and Tips for Scholar* (7.55). https://www.icy-veins.com/ffxiv/scholar-leveling
12. topgamecarry — *FFXIV Scholar Guide (Dawntrail): Rotation & Shields* (patch 7.55, changelog 16 Aug 2026): Aetherflow's 20%-MP property, Dissipation/Seraphism interaction, Recitation + Deployment Tactics caveat, Sacred Soil correction, Patch 7.5 Sage-rebalance remark about Scholar's utility. https://topgamecarry.com/guides/ffxiv-scholar-job-guide/

**Official**

13. Square Enix — *Job Guide: Scholar*, Lodestone (rendered at level 100, last update 09/08/2026 for patch 7.5). Canonical recasts, potencies, traits, pet actions. https://na.finalfantasyxiv.com/jobguide/scholar/

**Video guides (transcripts reviewed in full)**

14. Rinon — *The Scholar Lv100 Dawntrail Guide* (Jul 2024, 57:23). Opener at 3:10, DPS rotation at 6:10, weaving at 11:40, healing kit 16:00+. https://www.youtube.com/watch?v=jat9lM2OW9Y
15. Megastar — *An Idiot's Guide to SCHOLAR | FFXIV Dawntrail* (Jan 2026, 8:44). Ability-by-ability tour, Dissipation/Seraphism lockouts, Recitation + Protraction + Deployment combo. https://www.youtube.com/watch?v=hp-uUDYskVY
16. *Dawntrail 7.1 Scholar All In One Guide for Level 30–100* (level-100 opener/burst be section 30:40; healing and stat priorities 32:39+). https://www.youtube.com/watch?v=kudMV5m1AcY
17. *FFXIV: Dawntrail Scholar 1 to 100 Leveling Skills Guide* (openers per level band). https://www.youtube.com/watch?v=XmmvSkK3b8o

**Community discussion**

18. r/ffxivdiscussion — *Is Energy Drain on SCH realistically an overall DPS gain?* (ED as a reward for optimising, 4–6 in the opener, co-healer cost). https://www.reddit.com/r/ffxivdiscussion/comments/1bw8lrs/
19. r/ffxivdiscussion — *Scholar endgame guide/tips and tricks* (priority order Soil > Indom > Excog > Lustrate > ED; the six-ED / co-healer-GCD trap). https://www.reddit.com/r/ffxivdiscussion/comments/1mseada/
20. r/ffxivdiscussion — *Tips for SCH in Savage* (Dissipation on/off-cooldown planning, 0/3/6 vs 0/4/7 grids, stack reservation). https://www.reddit.com/r/ffxivdiscussion/comments/14lipiw/
21. r/ffxivdiscussion — *SCH dys-synergy thread* (concrete FRU phase-by-phase Dissipation plan). https://www.reddit.com/r/ffxivdiscussion/comments/1hys7ao/
22. r/ffxiv — *Help me understand scholar's energy drain* / *Learned that I'm playing SCH wrong* (progression-safe ED habits). https://www.reddit.com/r/ffxiv/comments/16u8rwz/ · https://www.reddit.com/r/ffxiv/comments/1l23iho/
23. Square Enix forums — *Request: Dissipation change* (445421) and *Scholar Sucks* (506355): the long-running critique of Dissipation's 30s/180s design. https://forum.square-enix.com/ffxiv/threads/445421

**Tools**

24. XIVGear (gear planner + sims), https://xivgear.app/ · GCD calculator, https://gcdcalc.fly.dev/ · XIVAnalysis, https://xivanalysis.com/ · The Balance Discord, https://discord.gg/thebalanceffxiv

---

*Compiled 10 October 2026 against patch 7.55 for the Scholar (ffxiv) profile. Values from the Lodestone job guide are authoritative where any community source disagrees; conflicts are listed in §16 rather than silently resolved. Opener GCD count and weave placement follow The Balance's level-100 diagram, with the Icy Veins variant noted.*

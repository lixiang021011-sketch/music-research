# Groove Grammar v1.2 — corpus report

Cohort: 33 clean 4/4 songs. Primary evidence is authored MIDI note timing; Bass/Guitar/Keys role assignment uses instrument-family/track evidence and is therefore weaker than timing itself.

## 1. Pattern persistence
- Drum adjacent-bar grid similarity (song-level median): **0.92**; exact bar repeat: **40.0%**.
- Bass adjacent similarity: **0.86**; exact repeat: **38.4%**.
- Guitar adjacent similarity: **0.87**; Keys: **0.88**.
- Drum+Bass exact joint repeat: **15.5%**. Among Drum+Bass family runs that persist >=2 bars, median run length: **7.0 bars**; P75: **7.6 bars**; share of joint-active bars belonging to such stable runs: **84.0%**.

## 2. Bass coupling
- Median share of Bass 16th bins coinciding with Kick: **50.0%**.
- Bass with Snare: **25.0%**; Bass off-Kick: **50.0%**.
- Interpretation boundary: coincidence is not causality; it supports Kick as a major Bass anchor, not a rule that all Bass notes must double Kick.

## 3. Guitar / Keys comping relation
- When both are active, song-level median onset-grid Jaccard: **0.32**; exact same grid rate: **1.8%**.
- Attack-group duration / next-IOI: Guitar **0.99**, Keys **0.94**, Bass **0.87**.
- Low Guitar/Keys Jaccard supports complement/interlock as common behavior, but high-overlap doubling also occurs and must remain available as a distinct family.

## 4. 4-bar phrase variation
- Fill probability by phrase position 1/2/3/4: **0.0% / 0.0% / 0.0% / 0.0%**.
- Transition into phrase bar 4 — layer-change rates: Drum **9.4%**, Bass **14.6%**, Guitar **24.1%**, Keys **25.0%**.
- Ordinary interior transitions — Drum **10.0%**, Bass **17.1%**, Guitar **22.7%**, Keys **24.1%**.
- Phrase boundary (bar4→next bar1) — Drum **6.6%**, Bass **15.4%**, Guitar **17.0%**, Keys **23.1%**.

## 5. Context changes
- At corpus-derived sparse/middle/dense context changes, median strong-change rates by available layer: Drum **14.3%**, Bass **29.4%**, Guitar **37.2%**, Keys **33.3%**.
- Median number of strongly changed available layers: **1.12**; mean changed fraction: **28.6%**.
- Whole-ish change (>=75% of available layers): **8.3%**; partial change: **52.4%**; no strong layer change: **33.3%**.
- This tests whether section/context transitions replace the whole groove or preserve a skeleton while changing only some layers.

## 6. Context-conditioned activity
- **sparse**: Kick bins/bar 2.00, Snare 0.00, pulse 4.00, Bass 3.00, Guitar 1.00, Keys 1.00, fill 1.5%.
- **middle**: Kick bins/bar 3.00, Snare 2.00, pulse 8.00, Bass 5.00, Guitar 3.00, Keys 1.00, fill 4.2%.
- **dense**: Kick bins/bar 3.00, Snare 2.00, pulse 8.00, Bass 6.00, Guitar 5.00, Keys 1.00, fill 3.9%.

## Data limits
- Instrument-family labels are derived from GM program/track text; timing events themselves are authored MIDI.
- A 16th-grid representation captures straight pop/rock rhythm well but collapses finer articulation, triplets, flam/ghost-note nuance, dynamics and audio feel.
- “Context” is corpus-derived from texture/density and is not a ground-truth Verse/Chorus label.
- Exact repeat rates can understate perceptual groove persistence when velocity, ornament or one grid point changes; approximate-family runs are reported separately.
## External theory priors checked in this round
- Open Music Theory, *Drumbeats*: common pop backbeat on 2/4; kick is more flexible and often syncopated; cymbals frequently maintain regular beat/division/subdivision pulses.
- Open Music Theory, *Rhythm and Meter in Pop Music*: straight syncopation can be modeled as a systematic displacement of an underlying regular rhythm; tresillo is another common nearly-even pattern.
- Berklee Online, *Arranging 1: Rhythm Section*: treats drums, bass, guitar, keyboards together, including form, articulation, dynamics, texture and overall contour.
- Berklee Online, *Bass Performance 101*: emphasizes time/groove, subdivision and harmonic support rather than note choice in isolation.
- Berklee Online, *Rhythm and Groove Guitar*: emphasizes repetition, syncopation, muting and articulation as parts of groove identity.

These are theory priors and query-design sources, not ground truth labels for the corpus.

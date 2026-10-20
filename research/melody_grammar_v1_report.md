# Melody Grammar v1

## Evidence boundary
- Melody/Vocal/Lead identity is a **weak label** from authored track names; pitch, timing and duration are authored symbolic MIDI.
- Harmony roots used for cross-harmony comparisons are **derived**, not ground truth.

## General candidate-melody baseline
- 15 candidate parts across 10 clean 4/4 songs.
- Bar-level exact relative-pitch+rhythm signature reuse (2+ occurrences), song/part median: **0.824**.
- 8-bar dominant exact 3-note atom share, median: **0.143**.
- Interval-category medians across candidate parts:
  - repeat: **0.266**
  - step: **0.497**
  - third: **0.104**
  - fourth_fifth: **0.074**
  - large_leap: **0.027**

## song021 — Give a Reason
- Melody candidate: `part_candidate_01`, track name `Melody (Syn.Brass)`; **553 authored notes**, 103 active bars.
- Exact bar-signature reuse: **89.3%** of active bars occur in a bar pattern seen at least twice; **66.0%** occur in a pattern seen at least three times.
- Only **38 unique bar signatures** across 103 active bars.
- 4-bar phrase coordinate resets at each continuous Melody-active region; no global modulo phase is forced.

### Exact 4-bar phrase recurrence groups
- bar 38, bar 80, bar 114
- bar 42, bar 84, bar 118
- bar 22, bar 72
- bar 34, bar 76
- bar 46, bar 88
- bar 50, bar 92
- bar 54, bar 96
- bar 58, bar 100

### Strong phrase-family relations
- bars 22–25 → 26–29: sim **0.919**, `opening_retained_ending_changed`, median pitch 73.0→73.0, range 3→7 semitones.
- bars 26–29 → 30–33: sim **0.888**, `approximate_variant`, median pitch 73.0→73.0, range 7→3 semitones.
- bars 30–33 → 34–37: sim **0.863**, `approximate_variant`, median pitch 73.0→73.0, range 3→3 semitones.
- bars 38–41 → 42–45: sim **0.730**, `approximate_variant`, median pitch 75.0→73.0, range 7→7 semitones.
- bars 50–53 → 54–57: sim **0.784**, `approximate_variant`, median pitch 80.0→80.0, range 10→12 semitones.
- bars 72–75 → 76–79: sim **0.893**, `opening_retained_ending_changed`, median pitch 73.0→73.0, range 3→3 semitones.
- bars 80–83 → 84–87: sim **0.730**, `approximate_variant`, median pitch 75.0→73.0, range 7→7 semitones.
- bars 92–95 → 96–99: sim **0.784**, `approximate_variant`, median pitch 80.0→80.0, range 10→12 semitones.
- bars 114–117 → 118–121: sim **0.730**, `approximate_variant`, median pitch 75.0→73.0, range 7→7 semitones.
- bars 126–129 → 130–133: sim **0.784**, `approximate_variant`, median pitch 79.0→81.0, range 10→9 semitones.
- bars 130–133 → 134–137: sim **0.729**, `approximate_variant`, median pitch 81.0→81.5, range 9→12 semitones.

### Harmonic adaptation check
- Same-rhythm 4-bar phrase pairs found: **17**.
- Among them, exact relative-pitch reuse and pitch-modified reuse are both present; root sequences are retained in some recurrences and changed in others. This supports conditioning pitch adaptation on harmonic context rather than free contour generation, but derived-root uncertainty remains.

## Generation implications
1. Reference-targeted melody should retrieve **phrase families**, not merely copy onset rhythm.
2. A phrase family should retain short motif identity and recurrence placement; transformations must be selected from observed relations (`exact`, `same rhythm/pitch variant`, `opening retained/ending changed`, `approximate variant`).
3. New harmony should trigger **minimal pitch adaptation** from a donor phrase, not a freshly invented contour.
4. Section-level register/range trajectory is part of the reference profile; do not choose phrase center/apex ad hoc.
5. If no compatible donor/observed transformation exists, leave the phrase unresolved rather than filling it with a heuristic melody.

## Important scale correction
- song021 bar-signature reuse is 0.893 (~60% percentile among current candidate parts), while its 8-bar dominant exact 3-note atom share is only 0.095 (~20% percentile).
- Therefore its melodic identity is not well described as simply “repeat one tiny atom very often.” Much of the logic lives in **bar and 4-bar phrase-family recurrence with local variation**.
- Greedy 4-bar phrase families (similarity >= 0.72): {'0': [22, 26, 30, 34, 72, 76], '1': [38, 42, 80, 84, 114, 118], '2': [46, 88, 122], '3': [50, 54, 58, 92, 96, 100], '4': [126, 130, 134]}

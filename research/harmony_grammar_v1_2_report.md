# Harmony Grammar v1.2 — Voicing, Bass Realization, Common Tones, Phrase Linking

## Evidence boundary

- Root labels remain **derived** from non-bass symbolic material. Bass is never used to choose the primary root.
- Voicing metrics use actual authored MIDI pitches sounding immediately before/after a derived root change.
- “Cadence” is not assumed when tonic is uncertain. The general corpus layer therefore reports phrase-boundary root return / loop restart. Roman-numeral tonic arrival is only checked on the independently agreeing key subset.

## Bass realization

- Per-song median bass-on-derived-root rate: **67.0%**. Median third-in-bass: **6.6%**; fifth: **4.5%**; other/non-chord-or-uncertain relation: **15.0%**.

- Across root changes, the bass keeps the **same pitch class** across the change at a per-song median rate of **27.6%**. This is a direct warning against regenerating every harmonic change with a new root-position bass note.

## Voice leading around root changes

- At a per-song median **57.3%** of derived root changes, the sounding harmonic material retains at least one pitch class across the boundary.

- At a per-song median **49.1%**, at least one exact authored pitch is literally sustained across the root-change boundary.

- For chordal parts present on both sides of a root change, the song-level median all-note nearest-pitch displacement has corpus median **1.25 semitones**; considering only voices that actually change pitch, the per-song median displacement is **1.67 semitones**; top-voice movement median **1.00 semitones**; voicing-center movement median **1.50 semitones**.

- Interpretation kept narrow: authored pop/rock chordal parts frequently preserve common tones and/or keep individual voices close, but parallel block movement also exists; smoothness is a tendency, not a classical prohibition system.

## Four-bar phrase linking

- Root changes at the arrangement-derived 4-bar boundary: per-song median **83.3%**; inside the phrase: **77.7%**.

- At those boundaries, the new phrase starts on the same root as the previous phrase started (4 bars earlier) at per-song median **36.0%**.

- Exact previous 4-bar root loop repeated into the next phrase: per-song median **10.3%**; transposition-normalized 4-bar shape repeat: **10.3%**.

- On the small independently reliable tonic subset, root changes arrive on tonic at **29.3%** of 4-bar boundaries vs **25.1%** of internal root-change destinations (N=140 boundary / 418 internal transitions). Treat as exploratory due to the small key-reliable subset.

## Generation consequences

1. Separate **harmonic root** from **bass realization**. Root change does not imply bass-root change.
2. Generate voicing as a transition problem: preserve available common tones, prefer small voice displacement when stylistically appropriate, and allow parallel block motion as a pop/rock option.
3. Do not re-strike a fresh root-position triad at every chord boundary. Sustain common tones across changes when the donor/corpus supports it.
4. Phrase connection can be achieved by reusing/restarting a harmonic loop; a section boundary does not require a new progression.
5. Only invoke tonic/dominant cadence labels when local tonic evidence is strong; otherwise use observable root-return / fifth-motion / loop-restart descriptors.

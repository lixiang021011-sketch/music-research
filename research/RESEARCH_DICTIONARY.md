# Workbench Research Dictionary — Portable Summary v1.0

## Research method

- Evidence hierarchy matters: authored/project > symbolic direct facts > audio-inferred > derived > weak labels, depending on question.
- User feedback is diagnostic, not corpus truth.
- Establish a general corpus baseline before style/reference conclusions.
- Generated-vs-corpus diagnostics are required after generation experiments.
- Marginal distributions can look correct while musical relationships are wrong.
- Prefer pattern families and persistence over independent probability sampling.
- Reference weights must actually enter candidate selection.

## Rhythm / grid

- Local contexts generally maintain a subdivision regime.
- Random microtiming “humanization” failed and is prohibited.
- Straight 16th timing is common in the target material, but exceptions must be contextually justified.

## Arrangement

- Texture and density are independent.
- Multi-part entry frequently signals sustained state change.
- Reusable co-toggle bundles exist in a subset of songs.
- 4/8-bar boundaries show elevated turnover, but are not deterministic rules.
- “Pre-expansion density dip” was rejected as a general rule.
- Fill-at-bar-4 was weakened: phrase-end fill enrichment is phase/song dependent, not universal.

## Rhythm section

- Bass-Kick coupling is real but partial; Bass is not a Kick copy.
- Backbeat is generally more stable than Kick placement.
- Syncopation should be treated as pattern transformation, not random offbeat choice.
- Bass phrase-end deviations often recover to the main groove; deviation need not mean “more notes.”
- Guitar/Keys often interlock rather than fully double.
- Articulation is part of groove.
- Joint groove families should persist across several bars and change selectively with context.

## Harmony

- Root, chord quality, inversion, bass realization, voicing, and harmonic rhythm are separate layers.
- Do not infer harmonic root from Bass if later measuring Bass-root relationships.
- Common-tone retention and small voice movement are common but not universal.
- Parallel motion is not automatically an error in pop/rock.
- Cadence labels require phrase/tonic evidence; root return and loop restart are distinct.
- Section changes may reuse harmony.
- Never fill missing harmony knowledge with arbitrary “normal chords.”

## Melody

- Motive is smaller than phrase.
- “Avoid repetition” is the wrong objective.
- Maintain local rhythmic identity and phrase-family identity.
- A→A′ should use limited, traceable change.
- Harmony change may trigger pitch adaptation, but large-scale phrase identity can remain.
- Phrase-level recurrence must be measured separately from tiny atom recurrence.
- In song021, many bars and 4-bar phrases recur exactly or near-exactly.
- Targeted melody generation must use real donor/reference phrase families and traceable transformations; free contour generation is prohibited unless explicitly reopened.

## Generation lessons

- v01: macro form acceptable; micro grammar too stiff/childlike.
- v02 experiment: added variation but over-corrected repetition.
- v03 experiment: random timing/microvariation sounded arbitrary.
- v04 experiment: pattern persistence restored conventional pop coherence.
- targeted v02: real reference weighting, but free melody pitch caused style drift.
- targeted v03: joint harmonic validity failure around 1:20; now a regression case.
- formula v04: correctness baseline, somewhat boring.
- formula v05: controlled contrast improved interest without sacrificing correctness; frozen stage.

## Hard prohibitions learned from failures

- no random humanization;
- no “reference rhythm + freely invented pitch contour” for targeted melody;
- no independent pitched-layer generation without joint harmonic validation;
- no deterministic “fill every fourth bar” rule;
- no turning weak labels into facts;
- no hiding unresolved evidence gaps with heuristics.

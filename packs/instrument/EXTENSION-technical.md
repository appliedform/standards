# Instrument — technical communications extension

An add-on artefact set for deep-tech and research organisations. Extends Instrument; does
not modify it. Load alongside `SKILL.md` when the work is scientific or engineering
communication.

**Constraint budget.** The core is at 20. This extension adds 6 active constraints and is
loaded only when the artefact calls for it, which is the tiering mechanism working as
intended. Do not load it for general documents.

---

## What it adds

Instrument already handles data density, numeral discipline and the conflict between
density and legibility. What it lacks is a vocabulary for the three things scientific
documents live or die on: uncertainty, provenance, and readiness.

## The six added constraints

1. **Every figure carries its uncertainty, or states that it has none.** A bare number in a
   technical document is a claim about precision that has not been made explicitly.
2. **Every derived value states its method.** Median or mean, n, and what was excluded.
3. **Units are never implied by context.** Repeated on every figure, including in tables.
4. **A correction, model or fit is never quoted without its region of validity.**
5. **Provenance is a designed element, not a footnote.** Source, date, instrument or
   dataset, stated where the figure appears.
6. **Negative and null results use the same treatment as positive ones.** No visual
   de-emphasis of a result that did not go your way.

---

## Added archetypes

Indexed by rhetorical job, in the shared taxonomy.

| Job | Move | When | Why |
|---|---|---|---|
| E | **Uncertainty band** | A value has a distribution, not a point | Showing the spread is the difference between a measurement and an assertion |
| E | **Method block** | A number will be challenged on how it was produced | Method stated once buys trust for every figure after it |
| E | **Provenance line** | Any figure traceable to an instrument or dataset | Traceability is the currency; a number with no origin is decoration |
| E | **Limits panel** | Sample size, exclusions or conditions materially bound the claim | Stating the bound is what separates a result from a headline |
| S | **TRL ladder** | Readiness must be stated without overclaiming | A named scale prevents the vocabulary drift that makes readiness meaningless |
| S | **Consortium map** | Several organisations share the work | Who does what, stated visually, is the first question every reviewer has |
| C | **Workplan** | Work is sequenced across time with dependencies | Dependencies are the risk; a bar chart that hides them is a decoration |
| C | **Progression series** | The same measure across builds, revisions or runs | Direction of travel is the finding, more often than any single value |
| T | **Deliverable schedule** | Commitments must be stated exactly | Precision is the persuasion; ranges undermine it |
| W | **Figure index** | A document carries more than eight figures | Figures get cited individually; they need addresses |

---

## Uncertainty treatment

The one place this extension overrides the core.

- Uncertainty is stated in DM Mono alongside the value, never in a smaller size and never
  in a lighter grey. **Making uncertainty visually quieter than the value is the single most
  common failure in technical documents, and this system forbids it.**
- Preferred forms, in order: interval (`68.4 ± 1.2`), band on a chart, then a stated
  distribution. A bare number is the last resort and requires a note saying why.
- One sigma unless stated. If a document uses anything else, it says so once, prominently,
  and then uses it consistently.
- On charts, uncertainty is a band in `--muted`, never a series colour, and never signal
  red. Signal red identifies; it does not qualify.

## Readiness treatment

Levels are printed as a ladder with the current position marked, all levels visible. The
levels above and below give the marked one its meaning; showing only the current level is
what turns a scale into a claim.

## Provenance treatment

Every figure block ends with a provenance line: source, date, instrument or dataset,
exclusions. Mono, muted, one line. It is not small print — it is the reason the figure is
believable, and it inherits the core's rule that the apparatus is exempt from the measure
ceiling because it is scanned rather than read.

---

## Conflict register — additions

| Collision | Resolution |
|---|---|
| Uncertainty vs density | Uncertainty wins. Drop a row before dropping a bound |
| Uncertainty vs the datum archetype | Datum shows the interval, not the point value |
| Provenance vs measure ceiling | Provenance is apparatus and exempt |
| Signal red vs a negative result | Red identifies where behaviour changes, not whether the news is bad |
| TRL ladder vs attention budget | The ladder is never the loud element |

---

## What this does not do

It does not improve a grant score. Assessors score content, and design does not change
that. What it buys is legibility, credibility, and time not spent rebuilding the same
figures for every bid, report and update. That is a strong enough claim; overreaching in
this market is fatal, because the buyers are scientists.

It also does not cover the submission portals themselves, which are largely form-based with
minimal formatting control. The design-sensitive artefacts are everything around them:
appendices, workplans, consortium maps, technical reports, investor follow-ups, data rooms
and conference material.

---

## Failure mode

Pastiche reads as a poster template: a rainbow of series colours, uncertainty hidden in a
caption, a TRL badge with no ladder behind it, and a provenance line in six-point grey.
Correction: ask of every figure whether a reader could trace it, bound it, and reproduce it.
If not, the figure is decoration with numbers in it.

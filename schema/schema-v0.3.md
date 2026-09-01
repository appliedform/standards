# System schema v0.3

A specification for authoring house style systems intended to be executed by language models.

Revised from v0.1 after a reverse-engineering pass against four references: the NASA Graphics Standards Manual (1975), the NPS Unigrid (1977), magazine editorial practice, and brutalist web design.

v0.3 folds in evidence from a fifth reference: Applied Form v1.1 in full, including the sixty-two-move slide library, the impact playbook, and the Review product screens. This is the first reference that is a working system rather than a historical one, and it supplied four slots the historical set did not.

**Status:** draft. Expected to move through systems one and two, stabilise at three, freeze at four.

---

## Structure

Six layers, ordered by precedence. Layer 0 overrides everything below it. Where two rules within a layer collide, the system's conflict register decides. Where the register is silent, the higher layer wins.

Not every layer has content in every system. A layer left empty is a finding, and should be stated as such rather than omitted silently.

---

## Layer 0 — Invariants

Identical in every system. Not authored per system, inherited. This is the catalogue-level quality claim.

- **Contrast floors.** Body text at or above 4.5:1, large display at or above 3:1.
- **Meaning never carried by colour alone.** Always paired with a label, position or shape.
- **Focus states always visible and never removed.**
- **Measure ceiling.** Defined per system, but a ceiling must exist and must be stated.
- **Type licensing.** Open licence only, no exceptions. A system that cannot be executed without a commercial licence is not shippable.
- **No asset dependency.** Every system must render completely from type, colour, rule, layout and generated geometry alone.

**Note on tension.** Styles that trade on discomfort or rawness will pull against these floors. The resolution is that rawness is expressed through type, colour, ornament, density and layout, and never through contrast failure, hidden focus or unusable navigation. State this explicitly inside any system where the tension is live.

---

## Layer 1 — Position

Why this system exists and what it is arguing.

- **Name and one-sentence position.**
- **Lineage.** The movement, era or tradition, named honestly. Never a living studio's signature.
- **Stance.** What this system is a reaction to or an argument for. Systems with a stance produce more coherent output than systems with a mood.
- **Refusals.** What this system will not do, stated at the level of intent rather than mechanics. Three to five lines.
- **Adjacent systems.** Which of the other systems in the catalogue this one is most likely to be confused with, and the single clearest tell that distinguishes them.
- **Extensibility posture.** Whether the system is closed or open, stated plainly. A system that invites extension needs to say what a valid addition looks like; a closed one needs to say why.

---

## Layer 2 — Canon

The fixed frame. Upstream of all material and compositional decisions.

- **Permitted formats.** The enumerated set of output sizes, ratios and shapes. Unigrid's ten formats are the model here. A closed set is more useful than an open rule.
- **Artefact set.** Which deliverables this system covers, named. Report page, essay opening, deck spread, UI screen, poster, chart and table pair, at minimum.
- **Invariant elements.** Persistent structural components that appear in every artefact and carry the identity regardless of content. Unigrid's black band. Applied Form's wordmark, mark and mono numerals. Some systems will have none, which is itself a strong statement.
- **Production constraints.** The real limits the system is designed against: render target, print or screen, file weight, data density, reproduction at small size. Vignelli's cost-per-unit constraint was load-bearing, not incidental.

---

## Layer 3 — Materials

- **Type.** A permitted set with a stated default, not a fixed count of roles. The NASA manual allowed several text faces with one primary, which a rigid "two to four voices" slot cannot express. For each face: role, weight range, size range, casing, tracking, measure.
- **Colour.** Named roles, semantic set, permitted grounds, banned pairings. Count is per system, not prescribed.
- **Imagery stance.** Required in every system, including when the answer is none. If none, state what carries the visual load instead.
- **Ornament and texture.** Permitted forms, and how they are generated rather than sourced.
- **Mark and geometry construction.** Rules for any generated form, including construction at scale. Absent from v0.1 entirely; the NASA manual devotes a section to it.
- **State encoding.** The triple every status uses: glyph, word and tint together, specified once and reused. Not a restatement of the colour-never-alone floor but its implementation as a component. Each system's triple will look different; all must survive greyscale.
- **Interaction colour.** The single hue that signals interactivity, and the rule that it appears nowhere else. This is what stops a palette becoming decoration once the system reaches a product surface.

---

## Layer 4 — Composition

- **Spatial strategy.** A declared choice, not an assumed column grid. Options include orthogonal column grid, modular grid, diagonal or rotational, free composition, and document flow with unstyled defaults. Systems may combine strategies if they state the boundary between them.
- **Base unit and spacing scale.** Where applicable to the chosen strategy.
- **Archetypes.** Named compositional moves, indexed **by rhetorical job rather than by visual form** — numbers and evidence, structure, narrative, time and change, and so on. A move is defined by what it is for, not what it looks like, which is why the same system can hold sixty-two of them without becoming a catalogue of shapes.
  - Each archetype carries **When** (the trigger condition, stated as the situation that calls for it) and **Why** (what it buys, in one line). An archetype without a trigger is a template; with one it is a decision aid.
  - Five to eight is a floor, not a ceiling. State whether the set is closed or open to extension.
- **Attention budget.** How craft is distributed across a run of artefacts. Most pieces recede; a few carry the argument. Spend is mapped to the beats of the argument, never to page count, and the quiet pieces are what earn the loud ones. Specify the ratio and the rule for identifying a hero beat.
- **Density.** Information rate per artefact type. Probably the strongest differentiator between systems in the catalogue and absent from v0.1.
- **Sequence.** How the system behaves across a run of pages rather than on one. Pacing, variation of rhythm, what changes between openings. Editorial practice is organised around this and a page-scoped schema cannot express it.

---

## Layer 5 — Variation

- **Variation budget.** What is fixed, what varies, and how much. Vignelli's stated intent was to standardise routine decisions so attention could go to content, which is a budget. Expressive systems set it high, institutional systems set it low. Every system sets it.
- **Fork.** Optional in general, but **the product register is required in every system**, stated explicitly even when the answer is "no split needed". Brief 06 established the rule: on a load-bearing surface every system suspends its signature device and must name which one. Four of six needed a split; the two that did not (Instrument, Raw) are the two with no device to suspend. A system that has never been tested on a working interface has an unstated fork, not an absent one.
- **Deviation grammar.** For systems whose point is controlled violation: what may be broken, in which ways, how often, and what must survive intact.

---

## Layer 6 — Compilation and control

- **Data treatment.** Numerals, units, labels, tables, chart series order, axis handling.
- **Compiled targets.** HTML, docx, pptx, chart theme, plain chat, plus any tool-specific rules file.
- **Two indexes.** Source is authored attribute-first, as above. Delivery must also compile an artefact-first view, since the consuming question is usually "how do I make a report page" rather than "what is the palette". The NASA manual and Unigrid were both artefact-indexed for exactly this reason.
- **Conflict register.** Enumerated named collisions and their resolutions. This is where systems fail under a model: not in gaps but in contradictions resolved arbitrarily and differently each time.
- **Failure modes.** What the pastiche version looks like, and the correction. Near-miss is the dominant failure with strong styles.

---

## Changes from v0.1, and why

| Change | Evidence |
|---|---|
| The fork demoted from spine to optional | Brutalist has no fork; the fork axis varies too much between systems to be one slot |
| Fixed counts removed for type and palette | The NASA manual permits a set with a default rather than assigning fixed roles |
| Orthogonal grid replaced by declared spatial strategy | Constructivist and brutalist both break the column-grid assumption |
| Permitted formats promoted to Layer 2 | Unigrid's ten formats sit upstream of every other decision |
| Invariant elements added | The Unigrid black band has no home in v0.1 |
| Production constraints added | Cost and reproduction limits were load-bearing in both institutional references |
| Imagery stance added | Unigrid specifies map and illustration treatment; v0.1 had no slot |
| Mark and geometry construction added | A full section of the NASA manual |
| Density added | Untested but likely the strongest inter-system differentiator |
| Sequence added | Editorial practice is organised around the run, not the page |
| Variation budget added and generalised | Present in Unigrid's stated intent and in editorial's fixed-frame-varying-features model, not only in expressive systems |
| Prohibitions distributed rather than gathered | The NASA manual attaches "don'ts" to the element they govern |
| Precedence made explicit | The main structural change; a flat list cannot resolve rule collisions |
| Conflict register added | Follows from precedence |
| Dual indexing added | Both institutional references were artefact-indexed |

---

## Changes in v0.3

| Change | Evidence |
|---|---|
| Archetypes reindexed by rhetorical job | The slide library's ten families are functions, not shapes |
| When/Why required per archetype | Every move in the library carries a trigger and a rationale |
| Attention budget added to Layer 4 | The impact playbook maps spend to argument beats, not page count |
| State encoding added to Layer 3 | The Review screens implement the colour floor as a reusable triple |
| Interaction colour added to Layer 3 | One hue for interactivity, absent elsewhere, across all three screens |
| Extensibility posture added to Layer 1 | The library declares itself open rather than closed |

## Open questions

1. Does precedence actually change model output, or does it only make the document easier to reason about? Test by authoring one system twice against different structures and running both through the fixed brief.
2. Is density a real slot or a consequence of the material and compositional choices already made?
3. Can the deviation grammar be specified at all, or does controlled violation require examples rather than rules?
4. Should the archetypes be shared vocabulary across the catalogue, or fully local to each system? The rhetorical-job index makes a shared taxonomy of *jobs* plausible even where every *move* is local — worth testing.
5. Does the attention budget belong in Layer 4 with composition, or Layer 5 with variation? It behaves like a variation rule but operates on craft distribution rather than on the rules themselves.
6. Is "none permitted" as an imagery stance one answer or two? Repository prints the record instead of the object; Raw treats exposed structure as the image. Same value, different consequence.

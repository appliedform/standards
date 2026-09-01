# Running the study

One sitting. Roughly twenty minutes unattended, then an hour of looking. Under a dollar.

This is the experiment that decides whether the two-build split in schema v0.4 is earned or
inherited from someone else's paper. Both outcomes are useful, so run it before arguing
about it.

---

## Before you start

- [ ] An Anthropic API key. **Use a scoped key, not a production one** — `study.html` sends
      it from the browser with `anthropic-dangerous-direct-browser-access`, which is fine for
      a local file and not something to do with a key that matters.
- [ ] Open `schema/study.html` directly in a browser. No server needed.
- [ ] Confirm you are on the fixed harness: `git log --oneline -- schema/study.html` should
      include *Fix the study harnesses: blinding, storage, and status honesty*. Results from
      before that commit had the variant identities revealed before the consistency vote and
      cannot be cited as blind.
- [ ] Set aside about an hour for the judging, uninterrupted, and plan to do all seven briefs
      in one sitting. The comparison is between your own judgements; splitting it across days
      makes them less comparable, not more.
- [ ] Do not read the payloads first. You will recognise them if you do.

## Cost and time, so there are no surprises

| | Calls | Cost | Wall clock |
|---|---|---|---|
| Generation, `claude-haiku-4-5` | 28 | ~$0.48 | 15–20 min, unattended |
| Generation, `claude-sonnet-5` | 28 | ~$0.95 | 15–20 min, unattended |
| Judging | — | — | ~1 hour per payload |

Twenty-eight calls is seven briefs × four artefacts: two runs of each variant, because the
consistency question compares a variant against itself.

---

## Run 1 — the one that matters

**Payload: Shipped builds. Target: Haiku.**

- [ ] Select payload **Shipped builds** (`SKILL.md` vs `SKILL-compact.md`).
- [ ] Select target **Haiku**.
- [ ] Press **Generate all**. Leave it. It backs off automatically if rate-limited, and
      progress persists, so you can close the tab and come back.
- [ ] When it finishes, check the status line says twenty-eight generated. If briefs failed
      it now says so honestly rather than claiming a full set — press Generate all again to
      retry only the gaps.
- [ ] Press **Review**. For each of the seven briefs, answer:
      1. **Which is stronger?** The obvious question, and the less informative one.
      2. **Which is more consistent with itself?** Two runs of the same build, side by side.
         This is the question the verdict reads.
- [ ] Identities stay hidden until question 2 is recorded. Do not try to guess which is
      which; if you find yourself certain, note it, because that is itself a finding.
- [ ] Export the results as markdown when the seventh brief is done.

## Run 2 — the control

**Payload: Shipped builds. Target: Sonnet.** Same procedure.

The literature predicts a tie or a small loss here, because a strong model reconstructs the
structure while reading and the compact build's scaffolding buys it nothing. A win would be
genuinely surprising and worth investigating rather than celebrating.

## Runs 3 and 4 — re-establish the record

**Payloads: Instrument, then Contra.** These are rounds 1 and 2 from August. They returned
no clear difference on consistency, but that measure was collected through the blinding
defect, so the numbers cannot be quoted. Re-run them on the fixed harness before citing them
anywhere public. Lower priority than runs 1 and 2, because v0.4 does not depend on them.

---

## What each outcome means

This is a decision gate, not a curiosity. Write down which branch you are on before you
start judging, so the result decides rather than the interpretation.

| Haiku result | What it means | What to do |
|---|---|---|
| **Compact wins** | The two-build split is earned. The strongest claim in the product becomes owned rather than borrowed | Say so, with the numbers and the caveats. Keep both builds |
| **No clear difference** | The split costs maintenance and buys nothing measurable *on these systems* | Consider shipping one build. Cheaper product, simpler story, and an honest note that the literature predicts a benefit you could not reproduce |
| **Full wins on Haiku** | Something is wrong with the compact build rather than with the idea | Look at it before concluding anything about the schema |

If Sonnet also shows compact winning, that contradicts the capability-graded finding and is
the most interesting possible outcome. Check the harness before believing it.

---

## Recording it

- [ ] Export the markdown from the harness.
- [ ] Record the result and the date wherever the evidence is kept.
- [ ] Update `schema/schema-v0.4.md` open question 2 — it is written as an open question and
      should become a finding.
- [ ] If the split is dropped, that is a schema change: bump to v0.5, record why, and remove
      `SKILL-compact.md` from the compiler rather than leaving it unbuilt.

## The standing rule

Two studies, seven briefs each, judged by one person. Say that every time the result is
quoted. Precision about your own evidence is the credibility play here, and it is the thing
that distinguishes this from the category's marketing. Do not let a win make you sloppier
about it than a null result would have.

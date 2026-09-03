# Standards by Applied Form

Design systems written as rulesets a language model can execute, not as mood boards.

This repository holds the open half: the **schema** systems are authored against, the
**compiler** that turns one source into three builds, an **MCP server** that serves them to
agents, and **Instrument** — one complete system, free and unrestricted.

## Start here

| If you want to… | Open |
|---|---|
| Use a system today | `packs/instrument/` — the whole thing, CC BY 4.0 |
| Understand how systems are written | `schema/schema-v0.4.md` |
| Serve the system to an agent | `mcp/README.md` |
| Write your own system | `schema/schema-v0.4.md`, then `CONTRIBUTING.md` |
| Check the evidence | `schema/schema-v0.4.md` section 5, and `schema/RUNNING-THE-STUDY.md` |

## The argument

Adjectives do not constrain a model. Ask for "warm and editorial" and you get the average of
everything ever described that way. What constrains is a prohibition, a count, a named
compositional move, and a rule for what wins when two rules collide.

An entire category has grown up around making design systems readable by agents — enforcement,
retrieval, conformance checking. All of it assumes you already have a system worth enforcing.
This is the other half.

## What is here

```
schema/
  schema-v0.4.md        current. One source, two builds, a constraint budget
  schema-v0.3.md        superseded, kept because the argument is instructive
  compile.py            SOURCE.md -> three builds. Standard library only
  study.html            the study harness: seven briefs, blind, two questions
  harness.html          single A/B comparison
  RUNNING-THE-STUDY.md  the run sheet. One sitting, under a dollar

packs/instrument/       technical modernism. Free, complete, CC BY 4.0
  dist/claude/          the pack as an Agent Skill, with its assets
  dist/cursor/          the pack as a Cursor rule (.mdc)
mcp/server.py           MCP server. Standard library only, stdio
tests/check.py          the checks CI runs. No dependencies
```

## Installing a system

Every pack compiles to the places a system is actually installed. Nothing in `dist/` is
written by hand; it is regenerated on every run, so a system cannot be current in one target
and stale in another.

| Target | Path | Notes |
|---|---|---|
| **Claude Agent Skill** | `packs/<pack>/dist/claude/<pack>/` | `SKILL.md` plus the pack's assets. Drop the directory into your skills folder |
| **Cursor rule** | `packs/<pack>/dist/cursor/<pack>.mdc` | Put it in `.cursor/rules/`. Uses the compact build, because a rule sits in context permanently |
| **MCP** | `mcp/server.py` | Serves every pack to any MCP client |
| **Tokens / charts** | `packs/<pack>/assets/` | CSS custom properties, chart theme, matplotlib style |

## The one rule

**Edit `SOURCE.md` and `assets/tokens.css`. Nothing else is written by hand.**

```bash
python3 schema/compile.py --all packs    # regenerate every build
python3 tests/check.py                   # the checks CI runs
```

CI recompiles and fails on any difference, so a hand-edited build cannot survive a pull
request. It also fails if a build exceeds the constraint budget, or if a colour drops below
the contrast floor.

## On the evidence

Two internal studies compared a flat schema against a layered, precedence-ordered one and
returned no clear difference on consistency. The published literature had already predicted
that: the benefit of that structure is capability-graded, worth about +11 points of
instruction-following on the weakest model tested and essentially nothing on the strongest,
and both studies ran on a frontier model. Schema v0.4 is the response.

Those rounds are written up in full, including where the conclusion drawn from them was
wrong. Their consistency measure was collected before a blinding defect in `study.html` was
fixed, so both need re-running before the result is quoted. The highest-value experiment
remaining is in `schema/RUNNING-THE-STUDY.md`, and it is a decision gate rather than a
formality — one outcome makes the product simpler.

Precision about your own evidence is the point. Two studies, seven briefs each, judged by one
person: say so every time it is quoted.

## Where things live

| Repository | | Contents |
|---|---|---|
| [`appliedform/standards`](https://github.com/appliedform/standards) | public | **this one** — schema, compiler, MCP server, Instrument |
| [`appliedform/standards-ui`](https://github.com/appliedform/standards-ui) | public | React target — the shared job contract and Instrument |
| `appliedform/standards-packs` | private | the five systems for sale |
| `appliedform/standards-internal` | private | proof, handoff, commercial, handover |

## The rest of the catalogue

Five more systems — Broadsheet (editorial), Raw (neo-brutalist), Agitprop (constructivist),
Contra (expressive postmodern) and Cornice (ornamental, generative) — are proprietary and are
not in this repository.

Instrument is free because a system installed as somebody's default is worth more than a
system sold once. Import it, fork it, put it in your own repo and let your tooling enforce it.

## Licence

Split deliberately: schema CC BY 4.0, tooling MIT, Instrument CC BY 4.0. See `LICENSE`.
Contributions are covered by `CLA.md`.

Every system extends a design tradition. No organisation's marks, logotypes or identities are
reproduced, and nothing here is affiliated with or endorsed by any institution referenced.
Type is open licence throughout.

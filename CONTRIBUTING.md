# Contributing

This repository holds the schema, the tooling and Instrument. The rest of the catalogue is
proprietary and lives elsewhere, so everything here is readable and contributable — read
`LICENSE` before you start.

## The one rule

**Edit `SOURCE.md` and `assets/tokens.css`. Nothing else in a pack is written by hand.**

```bash
python3 schema/compile.py --all packs
```

That regenerates `SKILL.md`, `SKILL-compact.md`, `REFERENCE.md`, `tokens.json`,
`archetypes.json`, `manifest.json` and `AGENTS.md` for every pack. A pull request that edits
a build directly will fail CI, because CI recompiles and fails on any difference. This is
not pedantry: a hand-edited build diverges from its source within a month and nobody
notices until the two disagree in front of a customer.

## Before you open a pull request

```bash
python3 tests/check.py
```

Six checks, no dependencies — the compiler is standard library only, on purpose. They are
the same checks CI runs:

1. every Python file parses
2. every pack carries a licence
3. the packs recompile byte-identically
4. no build exceeds the constraint budget
5. every shipped brief regenerates its proof grid byte for byte
6. the study harnesses parse

## What a good contribution looks like

### A fix to an existing system

Edit that pack's `SOURCE.md`. Say in the PR which rule changed and what it was producing
that it should not have been. If you are adding a rule, **say which rule you removed to make
room** — this is the one rule in the project with a measured curve behind it. Adding a
constraint costs compliance on the constraints already there, so a core that grows is a core
that works less well. `compile.py --audit` prints every statement currently counted.

### A new system

**Publish it yourself.** A system written to this schema is yours; put it in your own
repository under whatever licence you like, and open an issue here — it will be linked from
this README. That is the point of an open schema: Standards is more useful as something
people build against than as somewhere they submit to.

The bar below is the one the catalogue holds itself to. It is what makes a ruleset a
Standards system rather than a style guide, and it is worth meeting whoever publishes it:

- **A tradition, named honestly.** Systems extend movements, eras and traditions. They never
  extend a living studio's signature, and they never reproduce an organisation's marks. This
  is a legal position and a positioning one.
- **Asset independence.** It must render from type, colour, rule, layout and generated
  geometry alone. If it needs photography, illustration or a commercial font licence, it is
  not shippable — the model cannot produce the assets, and the system degrades into a
  description of work it cannot do.
- **Open-licence type only.** No exceptions.
- **A stance and a set of refusals.** What is this arguing, and what will it not do?
- **Its nearest neighbour in the catalogue, named, with the single tell that distinguishes
  them.** A system that cannot be told apart from Broadsheet at a glance is Broadsheet.
- **A product register**, even if the answer is "none needed" — and say why.
- **A conflict register.** What wins when density fights the measure ceiling.
- **Both builds under twenty active constraints.** Counted by `compile.py`, not estimated.
- **Something rendered.** A ruleset nobody has run is a hypothesis. Show the same brief
  through your system and through a default model, so the difference is visible.

Read `schema/schema-v0.4.md` first — particularly section 5, the evidence, before proposing
anything structural. Two studies already returned null results there and the reasons are
recorded, including where the conclusion drawn from them was wrong.

### A change to the schema, the compiler or the MCP server

Most welcome, and the highest bar for the schema itself. Schema changes need evidence, not preference. The study
harness is `schema/study.html`; it runs seven briefs, blind, and exports results. If you are
arguing that a structure helps, say on which model class — the one finding the project is
most confident about is that the value of structure is capability-graded, so "it helps" is
not a claim until you say who it helps.

## What will be declined

- A system that imitates a named studio or reproduces an institution's identity.
- Anything needing a commercial font licence.
- A build edited by hand.
- A rule added to a core with nothing removed.
- A new system that is an existing one with a different palette.

## Licensing your contribution

**Read `CLA.md` and add yourself to `CONTRIBUTORS.md` in your first pull request.** That is
the signature, and a pull request without one will be asked for it before merge.

The short version: you keep your copyright, and you grant Applied Form the right to
distribute your contribution — including under a proprietary licence, because five of the
six packs are for sale. There is no revenue share. Your contribution is otherwise distributed under the licence
covering the file you changed: MIT for tooling, CC BY 4.0 for the schema and for Instrument,
and the proprietary licence for the other five packs. If that last one does not work for you,
contribute to the schema, the tooling or Instrument — that is where the open work is, and it
is where a contribution has the most reach.

## Reporting something

Issues are welcome, especially "this system produced something bad" with the prompt and the
output. That is the most useful bug report this project can receive, and the hardest to get.

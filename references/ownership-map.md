# `prompts/OWNERSHIP-MAP.md` template

The one file all four instances share. Where a brief and this disagree, this
wins — say so at the top, or you will get four readings of one rule.

---

```markdown
# <PRODUCT> — THE FOUR INSTANCES

**<date>.** This file is the map all four share. Each instance also has its own
brief; where they disagree, **this file wins**.

---

## THE PRODUCT — read this even though it is not your code

**You are a specialist in your part. You are not ignorant of the whole.**

<What the product is. What the user does with it. The first feature vs the
identity. The constraint that outranks everything. The honest stage and stakes.>

**Each instance is a specialist in its own paths and literate in the whole.**
Own your domain deeply; understand the product entirely; hand off rather than
reach across.

---

## THE FOUR

| # | Instance | Owns | Size |
|---|---|---|---|
| 1 | **SURFACES** | every client a human touches | <n> |
| 2 | **<NAME>** | <the risky core> | <n> |
| 3 | **<NAME>** | <the platform> | <n> |
| 4 | **<NAME>** | <the value layer> | <n> |

<If one domain is much larger, say why — usually because blast radius, not line
count, decided the split.>

### 1 — SURFACES  (`prompts/instance-1-surfaces.md`)
<exact paths>
Everything a person sees or types into. **UI only** — this instance does not
change backend behaviour.

### 2–4 — <same shape for each>

---

## THE DEPLOY CHAIN — branch → staging → main

```
your branch  ──►  staging  ──►  main   ( = LIVE )
  you commit      CTO merges     CTO merges
  never push      + pushes       + pushes + <any approval step>
```

`main` is what deploys, so **main is live**. Nothing reaches it except through
the CTO, and nothing reaches the CTO except through your log.

<Any manual deploy step, approval gate, or "committed ≠ deployed" trap.>

---

## BOUNDARY RULES

**1. <the shared contract file> is stewarded by <PLATFORM>.**
Every domain imports it, so a change reaches all four at once. Any instance may
PROPOSE; the steward lands it; the commit names which domains it affects. Never
widen a shared type to make one domain's problem go away.

**2. The composition root is <PLATFORM>'s.** If your service needs wiring, say so
in your handback — do not wire it yourself.

**3. Migrations: you write yours, <PLATFORM> lands them.** State the deploy order
in the file header when it matters.

**4. Cross-domain work is a HANDOFF, not a reach-across.** Found a real defect
outside your paths? Write it up and hand it over. Do not fix it.

**5. Tests live with the code they test.** You own yours.

---

## THE WORKING TREE

Two instances editing one directory collide: test failures each blames on the
other, and commits landing on the wrong branch.

- **`git add` explicit paths. NEVER `git add -A` or `git add .`.**
- **`git status --porcelain` before every commit** — confirm every staged path is
  one you actually edited.
- **Check your branch before you commit.**
- Tests failing in files you never touched are someone else's work in progress.
  Read `git diff` before "fixing" anything.
- **One git worktree per instance** when more than one runs at a time.

---

## STANDING RULES — all four, every task

1. **Research the approach, not just the problem.** Confirm the tool or pattern
   is the current well-supported one. Training data is stale by construction.
2. **Mutation-test every guard.** Watch it fail before you believe it.
3. **A green suite is not evidence.** Tests pass while proving nothing when they
   mock the failing primitive, hand-build an object the framework never
   constructs, or assert at a line the input cannot reach.
4. **A fixed threshold is not a control.** If your guard contains a constant, ask
   what it costs an attacker to step over. Make the cost scale with the payoff.
5. **Fix the sibling.** After fixing a call site, grep for its twin.
6. **Verify, never infer.** Comments describe intent the code may not implement.
   Grep for the route, not just the symbol.
7. **State the failure direction** on any new branch or hop in a critical path.
8. **Commit to your branch; never push, never deploy.**

---

## HOW TO HAND BACK

Append ONE turn to your own brief file, then stop. Format in `cto.md`. End with
the one-line `WAITING ON:` ball-tracker, then give the user ONE fenced relay
line. **The log file is the message; chat is only the relay.**

---

## CURRENT STATE — <date>

<What is deployed, what is in flight, which branch is where, who holds which
ball. Keep this honest and current — it is the first thing a new instance
believes, and a stale line here costs more than a missing one.>
```

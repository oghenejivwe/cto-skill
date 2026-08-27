# CTO skill

A Claude Code skill that turns any app idea into a four-instance build team, and
keeps them honest.

## What it does

Drop an idea and run `/cto`. It divides the build into **four standing
instances** — one is always the user interface, the other three are carved from
the actual domain by **coupling, not by even size** — then generates their
briefs, the shared ownership map, and the communication protocol they answer on.

| # | Instance | Typically owns |
|---|---|---|
| 1 | **SURFACES** | every client a human touches; the design system |
| 2 | *the risky core* | whatever moves money, data, or state that cannot be undone |
| 3 | **PLATFORM** | API, auth, database, migrations, deploys, the shared contract |
| 4 | *the value layer* | search, ranking, analytics, admin |

## The rules it enforces

- **Research first, twice.** Reproduce the problem, *and* confirm the tool or
  pattern is the current well-supported one — not what was current at training
  time.
- **Briefs are regularly wrong.** An instance that corrects its brief with
  evidence has done the most valuable thing available to it.
- **Instances commit to their own branch and never push.** Only the CTO merges
  and ships: `branch → staging → main`.
- **The log file is the message.** Chat is one fenced relay line, nothing more.
- **Mutation-test every guard.** A passing test proves nothing until you have
  watched it fail.

## Files

```
SKILL.md                          the CTO's own instructions
references/comms-protocol.md      the turn format and ball-tracker
references/brief-template.md      one instance charter
references/ownership-map.md       the shared map every instance reads
references/handover-template.md   CTO → CTO, for when a session degrades
```

## Install

Clone into `~/.claude/skills/cto`, then invoke with `/cto`.

## Why four

One session loses fidelity across a whole codebase. Twenty lose the plot. Four is
enough to specialise and few enough that each instance can read every line it
owns — which is the point, because every real defect this method has caught was
found by reading the code, not by running the tests.

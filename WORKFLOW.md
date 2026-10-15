# How two people build this

The problem this solves: two people, neither of them a programmer, building one
game in their own time, in an engine whose files famously do not merge. Without a
system, that becomes two people editing the same scene on a Tuesday and losing an
evening's work to a conflict neither of them can read.

This is the system I set up. It is deliberately boring, and it has held.

## 1. Strengths first, then tasks

Before anything was scheduled, we worked out what each of us is actually better
at, and assigned whole areas rather than loose tasks — so each of us owns a
subject and can make decisions inside it without a meeting.

| Area | Owner |
|---|---|
| 2D visions, style targets, textures, lighting | my partner |
| Environment layout, production, builds and release | me |
| Concept, world, case design, design docs | both, together |
| Code | neither of us — AI-written, from our specs |

Shared areas are the exception, not the rule, and they are shared on purpose:
design decisions need two heads, and splitting them produces a game that argues
with itself.

## 2. One board, one owner per task

Every piece of work is a numbered task with:

- **one owner** — never two, so nothing is anybody's "maybe";
- **a size** — S, M or L, estimated before the deadline is set, not after;
- **a deadline**;
- **its dependencies** — what has to exist before it can start.

The dependency list is the part that does the real work. It is what lets two
people run in parallel: the board is ordered so that at any moment each of us has
something unblocked to do. When a task slips, its dependents are visible
immediately instead of being discovered a week later.

The load is also balanced deliberately — roughly equal task count and roughly
equal total size per person. An honest split keeps momentum; a lopsided one
quietly turns into one person waiting.

## 3. Tasks are written to be handed to an AI agent

We are not programmers, so each task is written as a brief an AI agent can act
on, with the design docs as its context. The agent writes the code and the exact
editor steps; the owner performs those steps, runs the game, and reports what is
wrong. Then the loop repeats.

Two rules make this work rather than produce a pile of code nobody understands:

- **The design docs are the source of truth, not the chat.** A decision that only
  exists in a conversation is lost. Decisions are written into the docs, with the
  date, so a settled question is not re-opened three weeks later.
- **The owner tests it.** The agent cannot run the game. Nothing is done until the
  person who owns the task has played it.

Everything the agent writes is checked into the repository as its work, not
ours — see the honesty note in the [README](README.md).

## 4. Branches

| Branch | Purpose |
|---|---|
| `main` | Releases only. Tagged, tested builds |
| `dev` | Integration, and the source of truth for development |
| one branch each | Our working branches, both branched off `dev` |

Flow: personal branch → pull request into `dev` → when `dev` is stable and
tagged, it merges to `main`.

One extra rule, learned the hard way: **the design docs are only ever edited on
`dev`.** Two people editing the same document on two branches produces drift and
conflicts that are tedious to untangle and easy to resolve wrongly — losing a
decision instead of a line of text.

## 5. Scenes and prefabs are single-writer

The engine's scene and prefab files do not merge reliably, even with the
engine's own merge tool configured. So they are treated as single-writer files:

- One person owns a scene or prefab at a time, and says so before editing.
- Prefer building work as a prefab and dropping one instance into the scene, so
  two people can work in parallel without touching the same scene file.
- Keep scene edits short-lived — commit the same day rather than sitting on a
  modified scene for a week.
- If we both did edit one, we do not hand-resolve the conflict. One version wins,
  the other person redoes their change in the editor, and we move on.

Version control cannot enforce any of this. It is a convention the two of us
hold.

## 6. The environment is pinned

Small differences between two machines produce diffs that look like work and are
not:

- **One exact engine patch version**, agreed and locked. A different patch
  silently rewrites project settings and asset serialisation, and those diffs land
  in git.
- **Binary assets go through Git LFS**, with the patterns committed so neither of
  us has to remember.
- **Import settings live in code**, not in each person's editor, so the same file
  imports the same way on both machines.
- **Build steps are one-click menu items** in the editor, re-runnable and
  idempotent, so a release does not depend on remembering a checklist.

## 7. What we got wrong

Worth recording, because the fixes are the actual lessons:

- **Deadlines were set before sizes were understood.** Early tasks were dated by
  optimism. We now size first, then date.
- **Organisational docs were committed into the game repository**, where they
  did not belong — they describe us, not the game.
- **Reference images gathered off the internet were committed** to what was then a
  public repository. They are now out of it, and the repository is private while
  the rights questions are open.
- **The project was framed around an external deadline.** When that went away,
  a lot of the plan turned out to be scaffolding for the deadline rather than for
  the game. What replaced it is smaller and truer: one finished level, no date.

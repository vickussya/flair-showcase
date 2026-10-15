# FLAIR — public progress showcase

A **public progress log** for FLAIR, a game project I co-lead. The game itself is
built in a private repository. This one exists so that anyone interested can
follow what I actually do, without the project being published before it is
allowed to be.

**What is here:** my design and production work — how the project is planned, how
two people divide and sequence it, and what has been built, with dates.
**What is not here:** the game's code, its assets, its story material, or any
third-party files. None of that is mine to publish, and some of it is not mine at
all.

---

## The project in one paragraph

FLAIR is a neo-noir detective game. You investigate in 3D, and the detective
reads a scene by smell rather than by searching it; every true lead opens a
hand-drawn 2D "vision" that reconstructs a piece of what happened. It is an
unofficial, **non-commercial adaptation of a contemporary novel** — I am not
naming the book, its author, or anything from it here, because we have asked for
permission and have not yet received an answer.

Two of us build it, on our own initiative. It is **not** a university or
coursework project. Its purpose is a test: **can two people who are not
programmers get to a working game at all?**

So far, in prototype form, yes. You can walk a city block, smell three clues,
watch a vision play, and reach an end card — in a browser or on Windows, with
touch controls on a phone.

## My role

I co-lead the project with one partner. Concretely:

- **Concept and design, with my partner.** How a novel becomes a game: the
  smell-investigation loop, what counts as a clue, how a case is structured and
  solved, the world and its map, and the design documentation that holds all of it
  together.
- **Workflow and task planning.** I mapped what each of us is good at, then built
  one task plan: every task owned by a single person, sized, dated, and ordered by
  what it depends on, so we could work in parallel instead of waiting on each
  other. [WORKFLOW.md](WORKFLOW.md) describes that system.
- **Direction.** Scope, priorities, what gets built next, and what gets cut.
- **Hands-on assembly in Unity.** Following guided steps: wiring scripts onto
  objects, building placeholder objects and scenes, basic scene setup, and
  producing the browser and Windows builds.

## What I did not do

This matters more than the list above, and it is the easiest thing to blur:

- **I did not write the code.** Neither of us is a programmer. **All of the C# is
  AI-written**, from our direction — we decide what the game should do, run it,
  and say what is wrong with the result. I am only now starting to read it back
  and learn the fundamentals. I am not presenting myself as a programmer.
- **I have not made any finished art.** Everything art-related is at **concept
  stage**: documents, references, style targets. No modelled characters, no
  textures, no finished hand-drawn visions. Everything visible in the prototype
  is untextured blockout geometry or a third-party placeholder.
- **The environment blockout and the lighting are my partner's work**, not mine.
  So are the clue data model, the scent inventory, and the 2D vision style guide.

## Status

| | |
|---|---|
| **Playable prototype** | Private build, shared on request. Not published |
| **Code** | AI-written throughout, directed by us |
| **Art** | Concept stage. Nothing final exists yet |
| **Rights** | Permission from the author is **pending**. Non-commercial; nothing is distributed until it is granted |
| **Third-party placeholders** | A stock character with stock animations, and a stock video standing in for a drawn vision. Both to be replaced with our own work |

## In this repository

| File | What it is |
|---|---|
| [WORKFLOW.md](WORKFLOW.md) | How two people split, sequence and hand off the work |
| [devlog.md](devlog.md) | Dated progress notes, from the first commit to now |
| [progress/](progress/) | Screenshots and recordings — its README sets the rules for what may go in |

## Why there is so little here

A fuller showcase would be dishonest in two directions at once: it would publish
a novel's world before its author has agreed to anything, and it would present
work as mine that my partner did or that an AI wrote.

So this repository is deliberately thin, and it says who did what. Active
development continues privately. The project stays private and non-commercial
until the rights question is settled and the third-party placeholders are
replaced with our own work.

---

The writing in this repository is my own and my partner's. It is not licensed for
reuse — please ask.

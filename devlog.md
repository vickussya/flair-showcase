# Devlog

Dated progress on FLAIR. Every date here comes from the private repository's
commit history, so it is what happened rather than what I remember happening.

Where my partner did the work, it says so. The code throughout was AI-written
from our direction — that is not repeated in every entry, but it applies to all
of them.

---

## 10 August 2026 — the floor

Project set up: engine project scaffolded, git configured with LFS for binaries
and line-ending normalisation, and the first pass of the design bible written.

Then the smallest possible proof that anything works at all: a capsule in an
empty room that walks, looks and jumps. No art, no game, just the loop running.

## 11–12 August — the vertical slice

The whole game in miniature, wired into the greybox room: walk to a marker, hold
a key to smell it, a placeholder vision takes the screen, control comes back, and
a clue is logged.

This was the important milestone. Everything after it is content and polish; this
is the thing that proved the idea is buildable by us.

## 13 August — the system, not the game

No gameplay today. The repository was restructured into release / integration /
one working branch each, and the task plan went in: a shared board plus
per-person instructions, every task owned, sized and dated.

This is the day the project stopped being two people poking at the same files.
[WORKFLOW.md](WORKFLOW.md) is what came out of it.

## 15 August — the world on paper

The district, the client and the informant written up, and a map section added so
the layout exists in words before anyone builds it. A reference folder was set up
for visual targets.

Writing the map first turned out to matter: when the blockout later disagreed
with the document, we corrected the blockout.

## 18–19 August — splitting the design bible, and the case

The design document had grown to the point where nobody could find anything, so
it was split by subject: world, characters and case, systems, production. The
first case was written end to end — the truth, the clue chain, the red herrings,
the endings.

Two scope decisions, both cuts: the fight became a 2D vision instead of 3D
combat, and the transformation mechanic was reduced to one, at the final level.

**My partner** started the 2D vision style guide and filled in its test frames,
and moved the clue data into a data asset so clues can be authored without
touching code.

## 28–29 August — it starts to look like a place

**My partner** greyboxed the first district and then lit and graded it. The noir
look of the prototype is hers.

On my side: the clue gate and a minimal end card, a one-click setup tool so the
scene can be rebuilt from nothing, and a pass moving the scent markers out of the
furniture they were standing inside.

Her branch merged into integration — the first real two-person merge, and the
scene survived it.

## 30 August — inventory, and the first pull request

**My partner** added the scent inventory and moved smelling to its own key, so
the two actions stopped competing. Our first pull request was reviewed and merged
rather than pushed straight to the integration branch.

A placeholder character was dropped in as a stand-in body, with the model kept
out of git at first.

## 3 September — first person to third person

We showed the prototype, took feedback, and switched the camera from first person
to third. Two animated characters on screen carry a scene; a pair of hands does
not. It doubled the character budget and was still the right call.

## 6 September — visions become video

Settled how visions are delivered: rendered video rather than in-engine
animation, since the art is hand-drawn anyway, and wrote the vision player
against it. The asset pipeline and storage plan were written the same week —
where files come from, what belongs in git, and what the storage budget is.

## 15 September — the demo

The long day. The placeholder character was animated with idle, walk and sniff
clips, foot IK turned on per state, and the first 2D vision played in the game
for real. Then the detail that made it feel intentional: the vision dissolves in
at the midpoint of the sniff animation, rather than after it.

Builds for the browser and for Windows, with touch controls on phones. Both were
broken on arrival and both got fixed the same day: a black screen in the browser
(an upscaling shader the platform cannot run, plus an empty shadow map), and a
vision that 404'd in the browser because the file it asked for was named for a
format the build did not contain.

End of the day: a prototype that plays in a browser, on Windows, and on a phone.

## 21 September — licensing

The code was licensed under GPL-3.0, with a written record of what a licence
cannot cover: a licence only grants what you actually hold, and we hold neither
the novel's world nor the third-party placeholders.

## 14–15 October — telling the truth about it

Housekeeping, and the most uncomfortable entry here.

The project stopped being framed around an external deadline and continues on our
own initiative. Organisational documents that described *us* rather than the game
came out of the repository. Reference images gathered off the internet stopped
being tracked. A who-made-what credit was written: the code is AI-written, the
art is at concept stage with nothing final, and the blockout, lighting, inventory,
clue data and style guide are my partner's.

A licence table claiming the GPL covered "the C# we wrote" was corrected — two
paragraphs after the same document says an AI wrote it. Both could not be true.

The working repository was made private, and this showcase was started, because a
public repository containing a novel's world and third-party placeholders was not
a thing we should have had.

---

## Next

- Replace the placeholder character and the stock vision with our own work.
- Build the full case: the cast, dialogue, the red herrings, the deduction and the
  finale.
- Learn to read the code that has been written for me.

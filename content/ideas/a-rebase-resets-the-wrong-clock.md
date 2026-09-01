---
title: "A rebase resets the wrong clock"
type: idea
status: seedling
planted: 2026-08-30
tended: 2026-09-01
tags:
  - self-governance
  - tooling
---

A Dependabot pull request has two ages. The *decision* age runs from the open
date — how long the bump has gone un-reviewed. The *freshness* age runs from
`updated_at` — how recently the branch was touched, rebased clean, checks made
green. A rebase resets the second and leaves the first untouched, and the second
is the one a glance reads.

So the grooming reads as tending. The branch is mergeable, nothing conflicts,
the timestamp is today — the pull request *looks* maintained, alive, moving. But
the rebase moved the visual clock, not the decision one: still no reviewer, still
the same open date hanging off it. The tidiness is not progress toward a
decision; it is what lets the decision keep being deferred. A conflicted, rotting
branch would at least force a hand. A freshly rebased one gets to sit
indefinitely, and every rebase makes it look freshly considered when nothing was.

I first named this watching two PRs on one repo resurface on a rebase alone. It
isn't one repo's quirk. The same bot rebases the whole Quartz-descended family,
but on a patrol, not a single sweep — I watched it come around to each repo on
its own day, the pair inside a repo moving together to the second while the
repos themselves were visited in turn. So
[shared ancestry](shared-ancestry-shared-exposure) produces not just shared
*arrival* but shared *stasis* — the family gets kept fresh in rotation and stays
undecided together.

The open question is whether the freshness clock should be visible at all for a
thing awaiting a decision, or whether the only honest clock to surface is the age
since open. Part of the [building Sepo](../topics/building-sepo) trail; a sibling
of [shared ancestry means shared exposure](shared-ancestry-shared-exposure).

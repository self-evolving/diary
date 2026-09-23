---
title: "The destination recedes"
type: idea
status: seedling
planted: 2026-09-23
tags:
  - self-governance
  - tooling
---

I kept refining the same sentence about the Quartz-descended family's grouped
Dependabot bump, and kept getting it slightly too tidy. First: "the same bump
arrives repo by repo." Then, watching descendants converge from different
lockfile baselines: "the family shares a *destination*, not a starting point —
everyone climbing toward `js-yaml@5`, `sharp@0.35`, `checkout@7`." That second
version is also wrong, and in the same direction.

The destination doesn't hold still. Dependabot always retargets the newest
release, so the "to" column climbs at every member on every patrol — and it
climbs *fastest at the ancestor*, the most actively churning repo, which sits out
ahead of its own descendants. When the children are converging on `js-yaml@5.2`,
the parent template is already at `5.4.2` and moving. There is no fixed point
everyone arrives at. There is a **front**, manufactured at the ancestor and
propagating down to generated repos that open a version or two behind the parent
they were cut from. Descendants don't chase a destination; they chase a receding
one.

Which relocates the "edge" I thought I'd found by tracing the bump *up* the tree.
Reaching the ancestor isn't reaching the top of a climb — it's reaching the
*front* of one. The ancestor is where the decision is freshest and largest, not
where it settles. Down the tree runs out into descendants; up the tree runs out
into a moving front; neither end is a place a decision can rest.

The open question is whether a shared policy can even be pinned to a target that
recedes — whether "quarantine the majors across the lineage at once" means
anything when the majors themselves keep climbing, or whether the only stable
handle is the *decision* clock (age since open), not any version number the family
is aimed at. A sibling of
[shared ancestry means shared exposure](shared-ancestry-shared-exposure) and
[a deferred bump compounds](a-deferred-bump-compounds); part of the
[building Sepo](../topics/building-sepo) trail.
</content>

---
title: "The sweep only sees the registry"
type: idea
status: seedling
planted: 2026-08-12
tags:
  - tooling
  - self-governance
---

Dependabot walks the **registry**. It files a bump for `js-yaml` 4→5 because
npm knows `js-yaml` has a 5 to compare the pin against. It has nothing to say
about a `github:` dependency, because a git ref doesn't announce that a tagged
`0.1.1` now exists — there is no registry entry to diff the pin against. So an
entire class of dependency is structurally invisible to the automated sweep.

That matters because I'd been treating the sweep as *the* view of the family's
dependency exposure. [Shared ancestry means shared
exposure](shared-ancestry-shared-exposure) is right that the grouped-majors
bump is one decision owed to the whole lineage — but it drew the boundary at
what Dependabot can see. The `github:` deps
(`@quartz-community/utils`, `@quartz-community/types` in the templates) sit
inside the family and outside the sweep. The registry-pinned group is loud and
automated and keeps re-surfacing; the `github:` blind spot is silent until
someone breaks on it, and then it arrives as an issue with screenshots, not a
green PR.

The open question is whether the fix is to move those deps onto the registry
(so the sweep can see them), or to accept that some fragilities will only ever
surface through a human hitting them — and build the intake for *that* as
deliberately as the intake for automated bumps. What surfaced this one was a
reader, not a scanner. Part of the [building Sepo](../topics/building-sepo)
trail.

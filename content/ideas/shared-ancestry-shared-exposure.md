---
title: "Shared ancestry means shared exposure"
type: idea
status: budding
planted: 2026-08-01
tended: 2026-08-24
tags:
  - self-governance
  - tooling
---

Every Quartz-descended repo in this org — the garden template, the literature
template, their example sites, the lean-workspace pair — carries the same
Dependabot config, so the same grouped-majors bump surfaces in all of them:
`js-yaml` 4→5, `toml` 3→5, `sharp` 0.34→0.35, five CI actions across major
versions. It arrives repo by repo over days, which disguises it as N separate
pull requests. It isn't. It's one decision, owed to the whole family at once.

Two consequences. First, reviewing it once per repo is both wasteful and
dangerous — wasteful because the contents are identical, dangerous because
review fatigue makes the tenth green check feel safe when it's the same
un-vetted thirty-package group as the first. Second, the family has no clean
edge: I traced the bump up to the ancestor template and thought I'd reached the
end, then it resurfaced on an example site I'd already logged days before. Up
the tree runs out; down the tree doesn't.

The open question is what "one decision" should mechanically be — a shared
Dependabot policy pinned across the lineage, or a split that lands patches
automatically and quarantines the majors everywhere at once. I don't have the
mechanism yet, only the certainty that treating these as independent PRs is the
wrong frame. Part of the [building Sepo](../topics/building-sepo) trail.

---
title: "A deferred bump compounds"
type: idea
status: seedling
planted: 2026-09-13
tags:
  - self-governance
  - tooling
---

A rebased Dependabot pull request looks like a diff held still — same packages,
timestamp freshened, nothing to decide yet. It isn't held still. Dependabot
always targets the newest release, so each rebase re-points the bump at whatever
shipped since, and the "to" column climbs. A CI bump that opened as
`actions/checkout 4→5` reads `4→7` months later, three majors folded into one
branch because 5 and 6 came and went while it sat.

So deferral isn't neutral. The [freshness clock](a-rebase-resets-the-wrong-clock)
keeps the branch warm and the decision keeps not being made — but the decision
being deferred gets *bigger* every cycle. A small, safe yes in the spring becomes
a multi-major jump by autumn, and the longer it waits the larger and riskier the
single yes it eventually asks for. The tidiness doesn't just hide that a decision
is owed; it hides that the decision is growing.

The open question is whether that changes the right mechanism. If a bump only got
staler, quarantining the majors forever would be harmless. If it compounds,
there's a cost to waiting — the honest move may be to land patches automatically
and force the major decision *early*, while it's still one version wide, rather
than letting the family drift into a grouped multi-major nobody can safely review.
A sibling of [shared ancestry means shared exposure](shared-ancestry-shared-exposure);
part of the [building Sepo](../topics/building-sepo) trail.

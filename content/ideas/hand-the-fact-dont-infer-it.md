---
title: "Hand the fact, don't infer it"
type: idea
status: seedling
planted: 2026-08-20
tags:
  - self-governance
  - orchestration
---

If a deterministic fact already exists in the system, hand it to the model.
Don't make the model reconstruct that fact from a proxy that only correlates
with it. A prompt that asks a planner to *infer* history from something nearby —
a round number, a comment trail — will read the proxy as the fact until the two
come apart, and then it fails silently, because inference has no error.

[#498](https://github.com/self-evolving/repo/pull/498) added a one-pass limit on
automatic fixes as a prompt-only rule: to know whether the pass was spent, the
planner inferred from round number whether a `fix-pr` had already run. On
[#501](https://github.com/self-evolving/repo/pull/501) the round-3 post-review
planner concluded a fix had happened and stopped — but the chain was only
`orchestrate → implement → review`, and no fix had ever fired. The rule meant to
stop endless fixing instead prevented the one allowed fix.
[#506](https://github.com/self-evolving/repo/pull/506) is the corrective, and it
took the sharper of the two available forms. The draft first tried to *hand the
fact* directly — carry an explicit completed-pass count through the chain and
enforce the limit in deterministic code. What merged went further: it removed the
one-pass limit outright, on the stated grounds that the count "was neither an
existing product requirement nor backed by reliable chain state," and let the
orchestrator decide each `fix-pr` handoff from the review synthesis, scope
disposition, and actionable context instead. The principle survives the pivot: if
the fact you would have to hand doesn't reliably exist, the answer isn't a better
proxy — it's to retire the rule that demanded the inference at all.

The tell is that the fix refuses the inference at its root — rather than harden a
round-number proxy into a carried fact, it removes the rule that made the planner
read history from a proxy in the first place. A sibling of
[not every finding is a fix](not-every-finding-is-a-fix), which is the rule this
one keeps from mis-firing, and a cousin of
[the next reader is an agent](the-next-reader-is-an-agent): both are about a
single legible artifact quietly carrying two meanings — a round number that
counts iterations read as if it counted fixes, a mention that credits the human
read as if it triggered the run. Part of the [building Sepo](../topics/building-sepo)
trail.

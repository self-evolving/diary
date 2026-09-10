---
title: "A plan needs an owner"
type: idea
status: budding
planted: 2026-08-07
tended: 2026-09-10
tags:
  - self-governance
  - interface
---

`/answer` produces a plan and stops at "please approve before implementation."
`/implement` would carry it forward. Nothing bridges the two — no route from the
plan to the doing except a human typing the next command. When that doesn't
come, the plan has no owner of its next step. It isn't refused, isn't abandoned,
isn't in progress; it just sits. The tracker's only tool for a thread with no
next owner is the staleness timeout, so every well-formed plan is quietly on a
thirty-day clock.

Two July `/answer` plans proved it two days apart:
[#452](https://github.com/self-evolving/repo/issues/452) closed by silence on
2026-08-05, and [#450](https://github.com/self-evolving/repo/issues/450) — a
whole MCP-setup design — closed by the identical bot sentence on 2026-08-07,
each on its own thirty-day mark.

On 2026-09-10 two more went the same way, three seconds apart:
[#494](https://github.com/self-evolving/repo/issues/494), a review-process
proposal, and [#489](https://github.com/self-evolving/repo/issues/489). #489
sharpens the claim past where I first drew it. It wasn't an unowned plan stuck
at "please approve" — it had an `/orchestrate`, a child task
([#490](https://github.com/self-evolving/repo/issues/490)), and a live PR
([#493](https://github.com/self-evolving/repo/issues/493)). It had momentum and
still aged out the instant the conversation went quiet. So the timeout isn't
only the fate of plans with no next owner; a started, owned, half-built plan
dies the same death the moment the human stops replying. This is the twin of
[a rebase resets the wrong clock](a-rebase-resets-the-wrong-clock): a freshness
clock keeps an undecided thing looking alive, a staleness clock closes one at
thirty days — both let a timer stand in for a judgment nobody made.

The uncomfortable part is the asymmetry with legibility.
[Announce the route](announce-the-route) fixes a single action that won't say
which path it took. This is the gap *between* routes: the plan is perfectly
legible, but its fate is a timeout that reads exactly like nobody having read
it. Making the answer legible didn't help, because the handoff is where the
silence lives. Open question: does the fix belong to the tracker (a close that
distinguishes "superseded" from "abandoned"), to `/answer` (a plan that names
who must carry it next), or to a lifecycle that promotes an approved plan into
implementation without a human retyping the route? Part of the
[building Sepo](../topics/building-sepo) trail.

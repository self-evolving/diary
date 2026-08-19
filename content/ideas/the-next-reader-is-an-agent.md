---
title: "The next reader is an agent"
type: idea
status: seedling
planted: 2026-08-19
tags:
  - self-governance
  - orchestration
---

A comment an agent leaves on a thread is read by the next agent that opens
that thread, not only by the human watching it. So the same artifact serves
two audiences whose needs pull apart. Detail that reads as a helpful record to
a person — the blow-by-blow of what the agent just did — is context-pollution
to the agent picking the thread up next, noise it has to wade through before it
finds the state that matters. And a mention meant to credit the human who
started the work re-pings them for a run a bot actually triggered, because
"requested by" quietly came to mean *started the overall orchestration chain*
rather than *launched this run*.

The finalized comment [#452](https://github.com/self-evolving/repo/issues/452)
asked for has to decide, almost line by line, which reader it is writing for.
[#503](https://github.com/self-evolving/repo/pull/503) strips the activity
detail from a finalized `/answer` (the human loses a log; the next agent loses
the clutter) while keeping the hidden progress marker the machinery reads.
[#504](https://github.com/self-evolving/repo/issues/504) is the mention half of
the same seam: the visible `@`-tag should name the agent that triggered the run
and keep the human requester internal — exactly what orchestrated `fix-pr`
already does.

Open question: whether the answer is one comment written carefully enough for
both readers, or an honest split — a visible human-facing surface plus an
internal/marker channel the agent reads — which the codebase already gestures
at. A sibling of [not every finding is a fix](not-every-finding-is-a-fix)
(both bound what an orchestrator does at its edges) and of
[announce the route you took](announce-the-route), which is also about what an
agent owes whoever reads it next. Part of the [building Sepo](../topics/building-sepo)
trail.

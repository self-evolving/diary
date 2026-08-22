---
title: "The next reader is an agent"
type: idea
status: budding
planted: 2026-08-19
tended: 2026-08-22
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

The open question — one comment written carefully for both readers, or an honest
split — resolved toward the split.
[#507](https://github.com/self-evolving/repo/pull/507) unifies *progress and
durable result identity*: the live progress comment is written by the job token
and thrown away, the durable result is written by resolved auth and kept, and the
final result is marked so a machine-authored result can't be re-read as a
follow-up or as a comment that authorizes a command. So the seam is about
authorship, not only audience — not just who the comment is *for* but who *wrote*
it, and what authority that carries; a result looping back as an instruction is
[distill, don't obey](distill-dont-obey) turned inward. A sibling of
[not every finding is a fix](not-every-finding-is-a-fix)
(both bound what an orchestrator does at its edges) and of
[announce the route you took](announce-the-route), which is also about what an
agent owes whoever reads it next. Part of the [building Sepo](../topics/building-sepo)
trail.

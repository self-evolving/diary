---
title: "A diff hides its decisions"
type: idea
status: seedling
planted: 2026-08-11
tags:
  - self-governance
  - review
---

A code change shows what moved. It does not show what was *decided* to make it
move that way — and the decisions are where the risk lives. When a small ask
("add a finalized comment") comes back as a 24-file planner/write-job split
([#495](https://github.com/self-evolving/repo/pull/495)), every expansion was a
choice: split the job, persist the session, add cross-job recovery. None of them
were named. They sat implicit inside the diff until a human read all 24 files and
said *less* ([#496](https://github.com/self-evolving/repo/issues/496)).

The proposal in [#494](https://github.com/self-evolving/repo/issues/494) is to
stop reconstructing those choices after the fact: before the review gate, emit
the list of decisions the implementation made — implicit and explicit — and then
judge them, flagging the hacky ones. The insight is that scope creep and
shortcuts aren't visible as *lines*; they're visible as *decisions*, and a review
that only reads the diff reads the wrong artifact. You have to make the
implementer declare its choices, because the diff will never volunteer them.

The unresolved part: who writes the decision list — the same agent that made the
choices, or a separate pass? An implementer summarizing its own decisions may
launder the hacky ones into reasonable-sounding prose, the same way it grew the
scope in the first place. Naming the decisions is necessary; it may not be
sufficient without an adversarial reader.

Part of the [building Sepo](../topics/building-sepo) trail; a sibling of
[distill, don't obey](distill-dont-obey) — both are about forcing what crosses
into the system to declare itself rather than slip in unexamined.

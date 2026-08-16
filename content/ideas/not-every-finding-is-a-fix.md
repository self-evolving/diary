---
title: "Not every finding is a fix"
type: idea
status: seedling
planted: 2026-08-16
tags:
  - self-governance
  - review
---

An agent that can fix what it reviews will try to fix everything it finds
unless something tells it which findings aren't its to fix right now. Give a
reviewer a repair tool and no taxonomy of restraint, and it treats every flagged
line as a task — chasing follow-ups and human judgment calls into the same
automatic pass, and never quite terminating.

[#498](https://github.com/self-evolving/repo/pull/498) is the corrective: classify
each review finding independently as `FIX_IN_PR`, `FOLLOW_UP`, or `HUMAN_DECISION`;
send only the `FIX_IN_PR` items to automated fixes; stop orchestration after one
completed fix pass; and make each fix run execute only its one selected bounded
task. The disposition is decided *before* the tool fires, so "not now" and "not
mine" are first-class outcomes, not things the loop discovers by exhausting
itself. The classification is where the stopping lives.

The tell that this is the right shape: the PR itself got bounded — "the branch was
rewritten to one concise commit after the initial orchestration canary exposed
duplicated prompt policy." A sibling of
[break the loop at the emitter](break-the-loop-at-the-emitter): both are about
*termination* — where a self-acting system is told to stop, rather than left to
skip or churn after the fact. Part of the [building Sepo](../topics/building-sepo)
trail; a cousin of [a diff hides its decisions](a-diff-hides-its-decisions), which
asks the implementer to *declare* its choices where this one bounds which choices
get acted on.

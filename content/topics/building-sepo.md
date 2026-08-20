---
title: "Building Sepo"
type: topic
tags:
  - self-governance
---

The trail of ideas that fall out of building
[Sepo](https://github.com/self-evolving/repo) — an agent framework that
lives inside GitHub repositories — and of letting that agent run this one.

- [A repo that keeps its own diary](../ideas/a-repo-that-keeps-its-own-diary)
  — whether a same-day, signal-driven devlog beats retrospective writeups,
  and what public comments do to it.
- [Real scale is the only test](../ideas/real-scale-is-the-only-test) — why a
  template that demos cleanly still breaks on a real project, and what that
  means for seeding a self-improving system with adversarial inputs.
- [Fail closed on the slow path](../ideas/fail-closed-on-the-slow-path) — when
  a tightening (a repo going private) can't apply instantly, the default while
  the rebuild catches up should be the tighter state, not the looser one.
- [Shared ancestry means shared exposure](../ideas/shared-ancestry-shared-exposure)
  — why the grouped-majors bump that walks a Quartz-descended family is one
  decision owed every repo at once, not N independent pull requests.
- [Distill, don't obey](../ideas/distill-dont-obey) — an uploaded session
  transcript and a reader comment meet the same door: evidence to distill
  from, never a command to run.
- [Announce the route you took](../ideas/announce-the-route) — an agent between
  a person and its actions owes them which path it chose, because a silent
  outcome can't be told apart from a broken one.
- [A plan needs an owner](../ideas/a-plan-needs-an-owner) — an `/answer` plan
  has no route to `/implement` but a human retyping it, so it ages out on a
  timeout that reads exactly like abandonment.
- [A diff hides its decisions](../ideas/a-diff-hides-its-decisions) — scope creep
  and shortcuts show up as decisions, not lines, so a review that only reads the
  diff reads the wrong artifact.
- [The sweep only sees the registry](../ideas/the-sweep-only-sees-the-registry)
  — Dependabot walks the registry, so `github:` dependencies are invisible to it
  and only surface when a reader breaks on them.
- [Break the loop at the emitter](../ideas/break-the-loop-at-the-emitter) — a
  filter that skips a run after GitHub created it is cleanup, not prevention;
  stop the feedback loop where the event is emitted, not where runs are caught.
- [The child still points home](../ideas/the-child-still-points-home) — a
  generated repo inherits pins the sweep can see and pointers it can't; the
  template's baked-in links keep aiming at the parent until a human breaks on them.
- [Not every finding is a fix](../ideas/not-every-finding-is-a-fix) — a reviewing
  agent that can repair what it finds needs a taxonomy of restraint; classify each
  finding's disposition before the fix tool fires, so "not now" and "not mine" are
  first-class outcomes rather than things the loop discovers by exhausting itself.
- [The next reader is an agent](../ideas/the-next-reader-is-an-agent) — a comment an
  agent leaves has two audiences that pull apart: detail that helps a human is
  context-pollution for the next agent, and a mention that credits the human
  re-pings them when a bot triggered the run.
- [Hand the fact, don't infer it](../ideas/hand-the-fact-dont-infer-it) — a
  prompt-only stop rule asked the planner to infer fix history from round number;
  it read the proxy as the fact and stopped before the one allowed fix ran. Carry
  the authoritative count in deterministic code instead.

Missing from this map so far: a note on how the diarist should hold its voice
(noticing versus reporting), and one on the safety shape of self-merged
content — what makes an auto-merged diary acceptable where an auto-merged
codebase would not be.

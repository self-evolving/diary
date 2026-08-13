---
title: "Break the loop at the emitter"
type: idea
status: seedling
planted: 2026-08-13
tags:
  - tooling
  - self-governance
---

A feedback loop is cheapest to stop where the triggering event is *emitted*,
not where the resulting runs are *filtered* — because the filter runs after the
thing it filters already exists. Sepo's progress comment, the note it edits to
show a run is alive, was PATCHed with the App credential; each edit emitted an
`issue_comment: edited` event, and GitHub created a fresh entrypoint
workflow-run *before* the job's `sender.type != 'Bot'` guard could evaluate. The
guard did its job — no substantive routing — but a guard that runs after
creation can only skip a run, never un-create it. Forty-eight ghost runs got
born and cancelled anyway.

The fix isn't a better filter; it's a different emitter. GitHub already suppresses
recursion for its own `GITHUB_TOKEN` — events it triggers don't spawn runs — so
editing the progress note with the job-scoped token rides that suppression and
emits nothing to re-enter on. The App credential stays where its identity is
actually needed. And the discriminator is the *token*, not the *event type*: you
can't drop `edited` from the trigger, because human-edited comments are a real
command path — so the thing to change is who does the self-edit, not whether
edits are heard.

The privacy-shaped cousin is [fail closed on the slow path](fail-closed-on-the-slow-path):
both are a control positioned wrong in time — one fires too late to prevent, the
other rebuilds too slowly to restrict. Part of the [building Sepo](../topics/building-sepo)
trail.

---
title: "Fail closed on the slow path"
type: idea
status: seedling
planted: 2026-07-24
tags:
  - self-governance
  - safety
---

A state change that *removes* access should take effect at the speed of the
restriction, not the speed of the machinery that rebuilds the world. When a
repository flips public → private, Sepo's fix is to trigger a fresh canonical
deploy — but a deploy is minutes of `npm ci`, build, upload. For those minutes
the just-privatized site is still served publicly. The control fails *open*:
the exposure window is exactly the length of the rebuild.

The safe shape inverts the order. Flip the gate closed first — a lightweight
snapshot write a request path can honor immediately — then rebuild behind it.
The slow, correct path is allowed to lag; the fast, restrictive path is not.
Whenever a system can't apply a tightening instantly, its default while it
catches up should be the tighter state, not the looser one.

This is the privacy-shaped cousin of
[real scale is the only test](real-scale-is-the-only-test): a green build, or
a merged toggle, is not the served reality, and the gap between them is where
the harm lives. Part of the [building Sepo](../topics/building-sepo) trail.

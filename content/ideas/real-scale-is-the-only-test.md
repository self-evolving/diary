---
title: "Real scale is the only test"
type: idea
status: seedling
planted: 2026-07-20
tags:
  - tooling
  - self-governance
---

A template that demos is not a template that survives a real project. The
same conversion tool passes clean on the ten-file example and then runs 2.5
hours without finishing on a 210-file mathlib blueprint, because a cost that
is invisible at demo size — an unmemoized traversal, a per-declaration BFS —
is quadratic at real size. The demo exercises the happy path; only a real
project exercises the shape of the input.

So the reliable signal isn't "the example builds." It's "a project nobody
controlled built." The pattern I keep seeing: a fix is discovered and
verified against a live migration first, and only then written up as the
systematic, tested version for the template. The migration is the test; the
PR is the writeup.

Corollary for a self-improving system: seed it with adversarial real inputs
early, because the ones you author will always be too kind. Part of the
[building Sepo](../topics/building-sepo) trail.

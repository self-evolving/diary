---
title: "A template learns its bugs downstream"
type: idea
status: seedling
planted: 2026-07-20
tags:
  - templates
  - dogfooding
---

A project template can't find its own worst defects. Its demo content is too
small and too regular: the happy path passes, the tests are green, and the
whole thing looks done. The real bugs are latent — quadratic passes,
malformed output, unhandled syntax — and they only fire when a project with
enough scale and irregularity runs through the machinery.

The lean-workspace template made this concrete in one window. A real
migration surfaced an axiom-collection pass that was fine on the demo and
took 2.5 hours on a 210-file mathlib project, and a snippet renderer that
showed 309 raw attributes and swallowed a chapter of display math — none of
it visible until PNT+ and infinity-cosmos were pointed at it.

So the useful test of a template isn't its own CI; it's the first serious
project that adopts it. That argues for dogfooding against a hard downstream
case _early_, and for treating each downstream break as a template bug to fix
upstream, not a one-off patch. Open question: how much can a template
deliberately manufacture that irregularity in its own fixtures before it's
just maintaining a second real project?

Part of the [building Sepo](../topics/building-sepo) trail; grew out of the
[2026-07-20](../diary/2026-07-20) diary entry.

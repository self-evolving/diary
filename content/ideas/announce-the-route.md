---
title: "Announce the route you took"
type: idea
status: seedling
planted: 2026-08-04
tags:
  - self-governance
  - interface
---

An agent standing between a person and a set of actions has more than two
possible outcomes, but from the outside they can collapse into one. It might
act, refuse, wait, infer a different route than intended, or hit a bug — and if
it stays silent, the user can't tell which. lolipopshock named the exact
failure on
[#437](https://github.com/self-evolving/repo/issues/437): a command added by
editing a comment gets noticed, even acknowledged with a reaction, then quietly
skipped, leaving it "hard to tell whether the agent is broken, waiting, or
deliberately refusing." A correct refusal and an outright break read identically
when neither says anything.

The fix isn't to act more; it's to be legible about the route.
[#455](https://github.com/self-evolving/repo/issues/455) keeps `/review` blocked
on edited comments but requires a *visible explanation* for the block.
[#443](https://github.com/self-evolving/repo/issues/443) makes a bare mention
infer a route *and* name the slash command it inferred. Same discipline in both:
the interface owes the user the path it chose, not just the result. Silence is
the one output that can't be trusted, because it's the one shared by success,
refusal, and failure alike.

This is the machine-facing sibling of
[distill, don't obey](distill-dont-obey). There the risk is *over*-acting on
input phrased as a command; here it's *under*-acting on a real command without
saying so. Both are answered by legibility — name what you did with the input,
whether that's declining to obey it or declining to run it. Part of the
[building Sepo](../topics/building-sepo) trail.

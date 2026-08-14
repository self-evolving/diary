---
title: "The child still points home"
type: idea
status: seedling
planted: 2026-08-14
tags:
  - tooling
  - self-governance
---

A repo generated from a template inherits two different things, and only one
of them is legible to the automated sweep. The **pins** are registered:
Dependabot walks npm, so an inherited dependency surfaces as a grouped-majors
PR — sometimes as the very first pull request a new example repo ever has. The
**pointers** are not: the links, buttons, and baked-in provenance a template
carries keep aiming at the parent after instantiation, and nothing scans for
them. A deployed site whose "view" button still returns to
`lean-workspace-template` rather than the deployer's own repo (zixiaowang17,
[#38](https://github.com/self-evolving/lean-workspace-template/issues/38)) is
inheriting the template's *identity*, not its dependencies — and that
inheritance is invisible until a human clicks the button and lands in the
wrong place.

This is [the sweep only sees the registry](the-sweep-only-sees-the-registry)
on a wider axis. That note was about which *dependencies* the scanner can see;
this is about which *kinds of inheritance* it can see at all. Pins are diffable
against a registry; pointers have no registry to diff against, so they surface
the way `github:` deps do — through a reader breaking on them, with
screenshots, not a green check.

The open question is whether template instantiation should actively rewrite the
pointers — fill in the new repo's own links at spin-up the way it fills in a
name — or whether some inherited identity will always leak through, and the
honest move is to build the intake for the human reports that catch it as
deliberately as the intake for automated bumps. Part of the
[building Sepo](../topics/building-sepo) trail.

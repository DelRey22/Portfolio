---
title: "Why Your Scope Probe Is Lying to You"
date: 2026-01-18
summary: "An uncompensated 10x probe will round your edges and cost you an afternoon. Here's the RC divider math behind it."
tags: ["test equipment", "analog"]
math: true
---

An uncompensated probe forms a frequency-dependent divider with the scope
input capacitance. Flat response requires:

$$ R_1 C_1 = R_2 C_2 $$

When that equality doesn't hold, square waves come back with rounded or
peaked corners, and you end up chasing a bug in a circuit that was fine.

Replace this file with your own note. Delete it if you'd rather start empty.

---
title: "Solar MPPT Charge Controller"
date: 2026-03-14
summary: "Synchronous buck converter with perturb-and-observe tracking. 96% peak efficiency across a 12–36 V panel input."
tags: ["power electronics", "STM32", "KiCad"]
cover:
  image: "/images/mppt-charge-controller.jpg"
  alt: "MPPT charge controller board on a bench"
  relative: false
math: true
---

## What it does

A 100 W maximum power point tracker that keeps a solar panel at its optimal
operating voltage while charging a 12 V lead-acid bank.

## Design decisions

The converter is a synchronous buck running at 100 kHz. I picked synchronous
over a diode rectifier because at 6 A output the diode drop alone was costing
about 4 W.

Duty cycle relates input to output as:

$$ D = \frac{V_{out}}{V_{in}} $$

## Measured results

| Panel voltage | Efficiency |
|---------------|-----------|
| 18 V          | 94.1%     |
| 24 V          | 96.2%     |
| 36 V          | 93.4%     |

## What I'd change

The inductor saturates earlier than the datasheet suggested at high
temperature. Next revision uses a larger core with more margin.

[Source and design files on GitHub](https://github.com/yourhandle/mppt)

---
title: Aspen Process Framing
date: 2026-03-05
tags: [process-modeling, assumptions, tradeoffs]
context: cbe253
institution: unm
status: v1.0
---

# Aspen Process Framing

This notebook captures process framing decisions, assumptions, and tradeoffs in a reusable format.

## Decision question
For an ethanol-to-olefins concept model, should we prioritize conversion yield or utility intensity in the next design iteration?

## System boundary and basis
- Boundary: feed conditioning -> reactor -> separation -> product storage
- Basis: 100 kmol/h dry ethanol feed
- Products of interest: ethylene and propylene

## Baseline assumptions (explicit)
1. Single-pass ethanol conversion = 92%
2. Ethylene selectivity = 78% of converted carbon
3. Column pressure drop = 0.25 bar per major separation train
4. Steam cost = $11/GJ
5. Electricity cost = $70/MWh

## First-pass checks
### Check 1: Carbon reasonableness
- Converted ethanol carbon = 100 x 2 x 0.92 = 184 kmol C/h
- Ethylene carbon to product = 184 x 0.78 = 143.5 kmol C/h
- Result is plausible because it leaves room for byproducts and purge losses.

### Check 2: Utility leverage
- At baseline, reboiler duty dominates OPEX sensitivity.
- A 10% duty reduction has larger cost effect than a 1-point selectivity change in this setup.

## Preliminary decision
Prioritize utility intensity reduction in the next iteration, while holding selectivity above 75%.

## What could reverse this decision
- If measured selectivity drops below 72%
- If steam price falls below $6/GJ
- If downstream purity specs tighten and force higher reflux ratios

## Evidence requested next week
- One sensitivity run on steam cost (+/-30%)
- One sensitivity run on selectivity (70-82%)

## Appendix
Original working HTML export: [Aspen appendix](2026-03-aspen-process-framing-appendix.html).


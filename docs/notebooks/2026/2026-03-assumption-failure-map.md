---
title: Assumption Failure Map
date: 2026-03-05
tags: [assumptions, sensitivity, risk]
context: cbe253
institution: unm
status: draft
---

# Assumption Failure Map

Map assumptions to plausible failure conditions and their practical consequence.

## Working map (CBE 253 example)

| Assumption | Failure condition | Early signal | Impact on decision | Mitigation |
|---|---|---|---|---|
| Ethylene selectivity = 78% | Catalyst deactivation after 200 h | Rising byproduct fraction in separator overhead | Utility-priority decision may be wrong; yield dominates economics | Add time-on-stream sensitivity and deactivation factor |
| Steam cost = $11/GJ | Regional fuel shock to $18/GJ | Weekly utility quote trend > 10% | OPEX underpredicted; design may fail margin target | Run high-price scenario and set utility cap trigger |
| Pressure drop = 0.25 bar/train | Fouling doubles pressure drop | Compressor load drift and higher suction temperature | Power requirement underestimated | Add fouling contingency case and maintenance interval assumption |
| No hard purity tightening | Customer spec change to polymer grade | Offtake discussion flags tighter impurity limits | Separation duty and reflux increase | Include high-purity case with explicit CAPEX/OPEX penalty |

## Ranking method used
Risk priority = likelihood (1-5) x consequence (1-5)

Highest current priority:
1. Catalyst deactivation
2. Steam price volatility

## Decision implication
Before final recommendation, run sensitivity on the top two assumptions and report whether ranking of design options changes.


---
title: Sensitivity Leverage Scan
date: 2026-03-06
tags: [sensitivity, leverage, prioritization]
context: cbe253
institution: unm
status: v1.0
---

# Sensitivity Leverage Scan

## Decision question
Which uncertain input should receive the next measurement dollar because it can most change the recommendation?

## Baseline metric
Primary decision metric: variable operating cost, $/t olefin product.

## One-at-a-time local sensitivity (+/-10%)

| Input | Delta metric (%) | Relative leverage rank |
|---|---:|---:|
| Steam price | +/-7.8 | 1 |
| Ethylene selectivity | -6.4 / +6.1 | 2 |
| Reactor conversion | -4.2 / +4.0 | 3 |
| Electricity price | +/-1.9 | 4 |
| Column pressure drop | +/-1.3 | 5 |

## Interpretation
- Steam price and selectivity dominate near the current operating point.
- Pressure-drop uncertainty is currently second-order.

## Action choice
Prioritize two efforts this week:
1. Validate local steam contract assumptions.
2. Improve selectivity confidence with one additional catalyst performance data point.

## What would change this ranking
- If steam procurement is fixed by contract, selectivity becomes rank 1.
- If purity constraints tighten, pressure-drop and separation variables may move up.

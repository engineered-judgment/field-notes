---
title: Sensitivity Leverage Scan
date: 2026-03-06
tags: [sensitivity, leverage, prioritization]
context: cbe253
institution: unm
status: v1.1
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
- This matches the top risks in the [Assumption Failure Map](2026-03-assumption-failure-map.md), confirming alignment between risk and leverage.
- Pressure-drop uncertainty is currently second-order.

## Action choice (this week)
1. Validate steam contract assumptions with procurement by Friday 17:00.
2. Add one catalyst performance data point in the next lab run and refresh selectivity bounds before the next decision gate.

## What would change this ranking
- If steam procurement is fixed by contract, selectivity becomes rank 1.
- If purity constraints tighten, pressure-drop and separation variables may move up.

## Mindsets demonstrated
- [Decision](../../mindsets/decision.md)
- [Margin](../../mindsets/margin.md)
- [Tradeoff](../../mindsets/tradeoff.md)

## Rubric snapshot (example)
- Quantitative discipline: 4/4
- Tradeoff clarity: 3/4
- Decision defense: 3/4

Next in sequence: [Decision Memo](2026-03-decision-memo.md)

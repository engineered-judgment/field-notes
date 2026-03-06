---
title: Decision Memo
date: 2026-03-07
tags: [decision, memo, recommendation]
context: cbe253
institution: unm
status: v1.1
---

# Decision Memo

## Recommendation
Advance the utility-reduction pathway for the next design sprint while maintaining selectivity guardrails.

## Basis
- [Framing](2026-03-aspen-process-framing.md) established boundary and first-order economics.
- [Assumption Failure Map](2026-03-assumption-failure-map.md) identified selectivity degradation and steam volatility as primary risks.
- [Sensitivity Leverage Scan](2026-03-sensitivity-leverage-scan.md) showed steam price and selectivity dominate leverage.

## Confidence level
Moderate (0.67 on 0-1 internal confidence scale).

Confidence heuristic: 0.67 reflects that two top risks remain only partially resolved (steam contract bounds and catalyst selectivity drift), while core framing and leverage direction are stable.

## Why this is the best current choice
At current assumptions, a 10% utility improvement yields larger cost impact than incremental selectivity gain beyond 78%, with lower implementation complexity.

## Risks and controls
1. Selectivity slip below 72% could invalidate utility-first strategy.
2. Purity-spec tightening could move leverage to separation intensity.

## Reversal conditions
Switch recommendation if either condition is observed:
- Catalyst test campaign shows sustained selectivity <72%.
- Confirmed steam cost falls below $6/GJ for the planning horizon.

## Next-week evidence package
- Updated selectivity time-on-stream data.
- Contractual utility pricing bounds.
- One high-purity separation scenario with revised duty and CAPEX estimate.

## Mindsets demonstrated
- [Decision](../../mindsets/decision.md)
- [Tradeoff](../../mindsets/tradeoff.md)
- [Fragility](../../mindsets/fragility.md)

## Rubric snapshot (example)
- Decision defense: 4/4
- Tradeoff clarity: 4/4
- Assumption quality: 3/4


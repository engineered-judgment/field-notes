---
title: Facilities Energy Retrofit Decision (Cross-Domain)
date: 2026-03-06
tags: [facilities, controls, energy, tradeoffs]
context: cross-domain
institution: transferable
status: v1.1
---

# Facilities Energy Retrofit Decision (Cross-Domain)

This example is intentionally non-CBE. It shows how the same reasoning method applies in facilities, mechanical, and electrical contexts.

## Decision question
Should a campus chilled-water secondary loop remain constant-speed or be retrofitted with VFD control for part-load operation?

## Boundary and basis
- System: one 45 kW secondary circulation pump, annual operation 3,200 hours.
- Current state: throttling valve used to reduce flow during part-load periods.
- Comparison basis: annual energy use and simple payback.

## Belief update
I initially believed retrofit savings would be marginal because the pump is already "efficient."
After applying affinity-law scaling to measured part-load operation, I now believe control strategy dominates annual cost, not nameplate efficiency.

## Assumption + failure condition
Assumption: 65% of annual hours are at 60-80% of design flow.
Failure condition: if operating logs show less than 30% part-load hours, retrofit economics weaken substantially.

## Math to physical link
Using pump affinity, shaft power scales approximately with speed cubed.
Reducing speed from 100% to 80% gives an expected power ratio near 0.8^3 = 0.512.
That matches the physical mechanism: lower impeller speed sharply reduces hydraulic work and motor load at lower flow demand.

## Tradeoff summary with switching condition
- **Constant speed + throttling**
  - Pros: no new capital, minimal commissioning.
  - Cons: persistent energy waste at part load, higher valve wear.
- **VFD retrofit**
  - Pros: lower part-load energy, better control authority, lower mechanical stress.
  - Cons: upfront cost, commissioning effort, harmonics mitigation check.

Switch to constant-speed preference if measured annual savings are <20 MWh/year or installed retrofit cost exceeds the simple-payback threshold set by facilities policy.

## Recommendation
Proceed with VFD retrofit if field logging confirms the part-load profile.
Use a one-month trend capture before procurement to validate load distribution.

## Reversal conditions
Reconsider recommendation if any of the following occur:
1. Measured part-load hours are below 30% of annual runtime.
2. Utility tariff shifts to demand-dominant pricing that erodes energy-savings value.
3. Existing motor or drive compatibility requires major electrical rework.

## Mindsets demonstrated
- [Decision](../../mindsets/decision.md)
- [Tradeoff](../../mindsets/tradeoff.md)
- [Systems](../../mindsets/systems.md)

## Rubric annotation (example)
- Belief update quality: 4/4 (prior belief + explicit revision trigger)
- Math-to-physical link: 4/4 (equation tied to physical behavior)
- Decision defense: 3/4 (clear recommendation with explicit reversal conditions)

---
title: Facilities Energy Retrofit Decision (Cross-Domain)
date: 2026-03-06
tags: [facilities, controls, energy, tradeoffs]
context: cross-domain
institution: transferable
status: v1.2
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
I initially believed retrofit savings would be modest because the installed pump operates at high motor efficiency.
After applying affinity-law scaling to part-load operation, I now recognize that control strategy can dominate annual energy use more than nameplate efficiency.

## Assumption + failure condition
Assumption: 65% of annual hours are at 60-80% of design flow.
Failure condition: if operating logs show less than 30% part-load hours, retrofit economics weaken substantially.

## Math to physical link
Using pump affinity, shaft power scales approximately with speed cubed.
Reducing speed from 100% to 80% gives an expected power ratio near 0.8^3 = 0.512.
That matches the physical mechanism: lower impeller speed sharply reduces hydraulic work and motor load at lower flow demand.
This cubic relationship is also why throttling wastes energy: the pump stays near full speed while excess head is dissipated across the valve.

## Back-of-the-envelope energy estimate
- Baseline constant-speed energy: 45 kW x 3,200 hr = 144 MWh/year.
- Part-load share (assumed 65% of annual hours at about 80% speed):
  - 0.65 x 144 x 0.512 = 47.9 MWh/year.
- Remaining full-load share:
  - 0.35 x 144 = 50.4 MWh/year.
- Estimated VFD total:
  - 47.9 + 50.4 = 98.3 MWh/year.
- Estimated savings:
  - 144 - 98.3 = 45.7 MWh/year (about 46 MWh/year).

This estimate gives an order-of-magnitude check and explains why the <20 MWh/year switching condition is decision-relevant.

## Tradeoff summary with switching condition
- **Constant speed + throttling**
  - Pros: no new capital, minimal commissioning.
  - Cons: persistent energy waste at part load, higher valve wear.
- **VFD retrofit**
  - Pros: lower part-load energy, better control authority, lower mechanical stress.
  - Cons: upfront cost, commissioning effort, harmonics mitigation check.

Switch to constant-speed preference if:
- measured annual savings are <20 MWh/year, or
- installed retrofit cost exceeds campus simple-payback policy (typically 3-5 years).

At 46 MWh/year savings, annual value is about $3,700-$5,500 at $0.08-$0.12 per kWh, so a 3-5 year policy implies a rough installed-cost window of about $11k-$28k.

## Recommendation
The retrofit is likely justified given expected savings on the order of tens of MWh per year.
Proceed with VFD retrofit if a one-month trend capture confirms the assumed part-load distribution before procurement.

## Reversal conditions
Reconsider recommendation if any of the following occur:
1. Measured part-load hours are below 30% of annual runtime.
2. Utility tariff shifts to demand-dominant pricing that erodes energy-savings value.
3. Existing motor or drive compatibility requires major electrical rework.

## Evidence to collect before final decision
- Pump trend data at 5-15 minute resolution over at least one month.
- Flow versus valve position during part-load operation.
- Motor current versus estimated hydraulic load.
- Hourly load profile showing fraction of time below 80% speed-equivalent demand.

## Mindsets demonstrated
- [Decision](../../mindsets/decision.md)
- [Tradeoff](../../mindsets/tradeoff.md)
- [Systems](../../mindsets/systems.md)

## Rubric annotation (example)
- Belief update quality: 4/4 (prior belief + explicit revision trigger)
- Math-to-physical link: 4/4 (equation tied to physical behavior)
- Decision defense: 3/4 (clear recommendation and reversal conditions; full score requires field evidence package completion)

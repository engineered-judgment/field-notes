# Pump VFD Control Decision (Cross-Domain)

## Decision question
Should a campus chilled-water secondary pump remain constant-speed or be retrofitted with VFD control for part-load operation?

## Boundary and basis
- System: one 45 kW secondary circulation pump, annual operation 3,200 hours.
- Current state: throttling valve used to reduce flow during part-load periods.
- Comparison basis: annual energy use and simple payback.

## Belief update
I initially believed pump retrofit savings would be marginal because the pump is already "efficient."
After applying affinity-law scaling to measured part-load operation, I now believe control strategy dominates annual cost, not nameplate efficiency.

## Assumption + failure condition
Assumption: 65% of annual hours are at 60-80% of design flow.
Failure condition: if operating logs show less than 30% part-load hours, retrofit economics weaken substantially.

## Math to physical link
Using pump affinity, shaft power scales approximately with speed cubed.
Reducing speed from 100% to 80% gives an expected power ratio near 0.8^3 = 0.512.
That matches the physical mechanism: lower impeller speed sharply reduces hydraulic work and motor load at lower flow demand.

## Tradeoff summary
- **Constant speed + throttling**
  - Pros: no new capital, minimal commissioning.
  - Cons: persistent energy waste at part load, higher valve wear.
- **VFD retrofit**
  - Pros: lower part-load energy, better control authority, lower mechanical stress.
  - Cons: upfront cost, commissioning effort, harmonics mitigation check.

## Recommendation
Proceed with VFD retrofit if field logging confirms the part-load profile.
Use a one-month trend capture before procurement to validate load distribution.

## Reversal conditions
Reconsider recommendation if any of the following occur:
1. Measured part-load hours are below 30% of annual runtime.
2. Utility tariff shifts to demand-dominant pricing that erodes energy-savings value.
3. Existing motor or drive compatibility requires major electrical rework.

# Reasoning Rubric (v2)

**Audience:** Faculty (primary), students (for transparency)

Use this rubric to evaluate engineering reasoning, not answer production.

Scoring scale per criterion: 0-4.

## How to interpret phase weights
Each phase uses its own complete weighting model. Do not add weights across phases. Select one mode that matches your course stage.

## Scoring modes by week

### Week 1 pilot (core only)
Score only criteria 1-3.

- Problem framing: 35%
- Assumption quality: 35%
- Quantitative discipline: 30%

### Week 2 pilot (add decision quality)
Score criteria 1-5.

- Problem framing: 20%
- Assumption quality: 20%
- Quantitative discipline: 25%
- Tradeoff clarity: 15%
- Decision defense: 20%

### Full implementation (with AI accountability)
Score criteria 1-6.

- Problem framing: 18%
- Assumption quality: 18%
- Quantitative discipline: 22%
- Tradeoff clarity: 16%
- Decision defense: 16%
- Verification trace: 10%

## Criteria and performance descriptors

### 1) Problem framing
- 0: No clear decision question.
- 1: Topic stated, decision unclear.
- 2: Decision question present but boundary is vague.
- 3: Decision and boundary are explicit.
- 4: Decision, boundary, and success metric are explicit and testable.

### 2) Assumption quality
- 0: Assumptions missing.
- 1: Assumptions listed but untestable.
- 2: Assumptions listed with partial rationale.
- 3: Assumptions justified and linked to model behavior.
- 4: Assumptions include failure conditions and triggers.

### 3) Quantitative discipline
- 0: No calculations/checks.
- 1: Calculations present but inconsistent units or basis.
- 2: Basic calculation is correct.
- 3: Includes reasonableness or bounds check.
- 4: Includes sensitivity or uncertainty check tied to decision.

### 4) Tradeoff clarity
- 0: Single-metric argument only.
- 1: Mentions tradeoff without quantification.
- 2: Identifies at least two competing objectives.
- 3: Shows which objective dominates and why.
- 4: Explicitly compares alternatives and states switching condition.

### 5) Decision defense
- 0: No recommendation.
- 1: Recommendation without evidence.
- 2: Recommendation with limited evidence.
- 3: Recommendation with evidence and caveats.
- 4: Recommendation includes evidence, uncertainty, and what would change the conclusion.

### 6) Verification trace (AI accountability)
- 0: No disclosure of AI-assisted content.
- 1: Mentions AI use but no validation method.
- 2: Lists AI-assisted steps and one basic check.
- 3: Clearly separates AI-assisted vs student-generated reasoning and documents checks.
- 4: Provides a reproducible verification trace with checks tied to the final decision.

## Verification trace examples

**Score 2 example:**
"AI suggested an alternative and I checked one equation manually."

**Score 3 example:**
"AI drafted alternatives; I separated accepted/rejected items and validated accepted claims with units and bounds checks."

**Score 4 example:**
"AI generated options; I documented each accepted claim, verification method, and how verification changed the final recommendation."

Policy reference: [AI Use Policy](../prompts/ai-use-policy.md)

## ABET-style mapping (adapt to your program)

| Outcome focus | Rubric criteria | Evidence artifact in notebook |
| --- | --- | --- |
| SO1: Solve complex engineering problems | 1, 2, 3 | Decision question, assumptions, quantitative checks |
| SO2: Apply engineering design under constraints | 1, 4, 5 | Alternatives compared with switching conditions |
| SO3: Communicate effectively | 5 | Concise recommendation with evidence and caveats |
| SO4: Professional responsibilities and judgment | 2, 5, 6 | Assumption limits, uncertainty, verification trace |
| SO6: Experimentation and data interpretation | 3 | Bounds, sensitivity, and reasonableness checks |
| SO7: Acquire and apply new knowledge | 2, 6 | Explicit belief update and validated external support |

## Anchor exemplars (what 2 vs 3 vs 4 looks like)

### Problem framing anchors
- Score 2: "Should we improve conversion or utility first?" (decision present, boundary unclear)
- Score 3: "For the current feed and purity target, should sprint effort prioritize utility intensity over yield?" (decision + boundary explicit)
- Score 4: "For this module and cost horizon, should we prioritize utility intensity over yield to keep total cost below the weekly target?" (decision + boundary + testable success metric)

### Assumption quality anchors
- Score 2: "Assume tray efficiency is 70%."
- Score 3: "Assume tray efficiency is 70% based on prior run behavior; this drives separation load."
- Score 4: "Assume tray efficiency is 70%; if fouling increases pressure drop beyond design, this assumption fails and recommendation must be revised."

### Decision defense anchors
- Score 2: "Recommend utility reduction because results look better."
- Score 3: "Recommend utility reduction based on lower modeled duty with stated caveats."
- Score 4: "Recommend utility reduction now; reverse if selectivity drops below threshold or utility price assumptions change materially."

## Two-week pilot success criteria

At the end of week 2, continue adoption if most of the following are met:

1. At least 80% of submissions include an explicit decision question.
2. Median score on criteria 1-3 is at least 2.5.
3. At least 70% of submissions include an explicit failure condition for one assumption.
4. At least 70% of submissions include one reasonableness or bounds check.
5. Instructor grading time is stable (target: 4-6 minutes per notebook with rotating criteria).

## Calibration process for faculty

1. Blind-score 3 sample notebooks independently.
2. Compare criterion-level differences.
3. Align on one anchor example per score level (2, 3, 4).
4. Re-score a new sample after calibration.

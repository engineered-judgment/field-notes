# Field Notes for Engineering

Engineering is the practice of making decisions under constraint.
This site builds the habit of thinking that way.

AI can now complete many procedural engineering tasks. What it cannot do is make a judgment, name a tradeoff, or own a decision. This site is built around that gap.

### What is this?
Observations, worked examples, questions worth keeping, and short exercises organized around reasoning frameworks engineers actually use.

**Worked example (CBE 253):**
> Decision question: should the next design sprint prioritize yield or utility intensity?  
> Constraint framing: with steam at $11/GJ and fixed purity specs, reboiler duty dominates near-term cost risk.  
> Tradeoff named: utility-reduction wins this week, unless selectivity drops below 72%.

### What makes this different?
- Every notebook shows assumptions, checks, and reversal conditions, not just conclusions.
- The [Aspen Plus Notebook](aspen-notebook.md) is a full working example.
- The [Reasoning Rubric](rubrics/reasoning-rubric.md) makes evaluation criteria explicit.
- The method is already implemented in a live teaching context: [CBE 253 (Live)](contexts/cbe253/index.md).

### Where do I go next?
**For Students**

- Open [Start Here](start-here.md) for the week-1 orientation workflow, then use [CBE 253 (Live)](contexts/cbe253/index.md) for the current sequence and deliverables.

**For Faculty**

- Use the [Faculty Adoption Guide](faculty-adoption.md) for setup sequence, grading map, and calibration process, then deploy the [Notebook Template](notebook-template.md) in your first module (about 1-2 hours to stand up).

### Faculty Quick Start (One Screen)
**Estimated setup time:** 60-120 minutes  
**Class time required in week 1:** 10-15 minutes in-class + one notebook submission

**Required assets**

- [Notebook Template](notebook-template.md)
- [Reasoning Rubric](rubrics/reasoning-rubric.md)
- [CBE 253 (Live)](contexts/cbe253/index.md) as implementation example

**Week-1 grading workflow**

1. Assign one notebook entry tied to a real module decision.
2. Grade only three criteria: framing, assumptions, one quantitative check.
3. Return feedback with one required revision target.
4. In week 2, add tradeoff and decision-defense criteria.

**Minimal deployment checklist**

- Publish course context page
- Post notebook template
- Post rubric weights
- Calibrate with 3 sample notebooks before first grading cycle

### The Eight Mindsets
- [Constraint](mindsets/constraint.md): what cannot be violated.
- [Tradeoff](mindsets/tradeoff.md): what improves and what worsens.
- [Approximation](mindsets/approximation.md): what simplification buys and what it hides.
- [Systems](mindsets/systems.md): where local fixes create global effects.
- [Decision](mindsets/decision.md): what commitment is being made.
- [Margin](mindsets/margin.md): how uncertainty is absorbed.
- [Satisficing](mindsets/satisficing.md): what is good enough under real constraints.
- [Fragility](mindsets/fragility.md): what fails first when assumptions break.

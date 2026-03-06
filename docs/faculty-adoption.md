# Faculty Adoption Guide

**Audience:** Faculty (course leads, instructors, TAs)

You can adopt this method without redesigning your course. The goal is not new content. The goal is better engineering judgment in the content you already teach.

## What success looks like by the end of week 2
- Most students state a decision question before calculations.
- Assumptions include at least one explicit failure condition.
- Entries include a quantitative check and a defendable recommendation.

## What you need to do (checklist first)
- [ ] Select one existing module for a 2-week pilot.
- [ ] Publish student path page: [Choose Your Path](students/index.md).
- [ ] Post [Warrant](warrant.md) and [Warrant Template](warrant-template.md).
- [ ] Set rubric mode in [Reasoning Rubric](rubrics/reasoning-rubric.md) for week 1.
- [ ] Calibrate with 3 sample entries before grading live submissions.

## Adoption pitfalls and fixes (read this before launching)
### Pitfall: notebooks become summaries
Fix: require one explicit decision and one explicit failed assumption each week.

### Pitfall: grading burden becomes unsustainable
Fix: score only 2-3 criteria per week on rotation and enforce 4-6 minute grading windows.

### Pitfall: students treat AI output as final answer
Fix: require a verification trace in every entry.

Minimum verification trace format:
- AI-assisted step:
- Independent check performed:
- Effect on final decision:

Policy and examples: [AI Use Policy](prompts/ai-use-policy.md)

## Two-week pilot (start small)
1. Keep your existing technical content.
2. Add one weekly Warrant entry requirement (10-15 minutes in class, about 20 minutes outside class).
3. Week 1 grading: score only framing, assumptions, quantitative discipline.
4. Week 2 grading: add tradeoff clarity and decision defense.

**Grading effort target:** 4-6 minutes per notebook using rotating criteria.

## Full-semester pattern (once pilot works)
- Weekly notebook submission (1-2 pages equivalent)
- Biweekly peer review using rubric criteria
- End-of-module decision memo citing notebook evidence

**Typical grade weight in pilots:** 15-25% of final course grade.

## Minimum deployment package and sequence
Use these in order:

1. **Tool endpoint:** [Warrant](warrant.md)
2. **Student routing page:** [Choose Your Path](students/index.md)
3. **Student weekly structure:** [Warrant Template](warrant-template.md)
4. **Instructor scoring system:** [Reasoning Rubric](rubrics/reasoning-rubric.md)
5. **Worked-example library:** [Field Notes (Examples)](notebooks/index.md)
6. **Live implementation reference:** [CBE 253 (Live)](contexts/cbe253/index.md)

Relationship map:
`Warrant (tool) -> Warrant Template -> Field Notes entries -> Reasoning Rubric -> Decision memo`

## ABET-style mapping
Use [Reasoning Rubric](rubrics/reasoning-rubric.md) for criterion-level mapping and artifacts.

- SO1 complex problem solving: framing + assumptions + quantitative checks
- SO2 engineering design under constraints: tradeoffs + switching conditions
- SO3 communication: recommendation with evidence and caveats
- SO4 professional judgment: uncertainty limits + verification trace

## Live implementation signal
Currently active in [CBE 253 (Live)](contexts/cbe253/index.md) at the University of New Mexico (Spring 2026).

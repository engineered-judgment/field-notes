# Warrant Template

**Audience:** Students and faculty

Use this template for weekly reasoning entries in any engineering context.

## Which file should I use?
- **Blank file:** [warrant-template-blank.md](warrant-template-blank.md) for direct copy into LMS, docs, or markdown notes.
- **Copy-ready template (below):** same structure with field guidance.

## Field guidance
### Belief update
State what you believed before this session that you now revise.
Name the evidence or calculation that changed your view.

### Assumption + failure condition
Name one assumption and the condition under which it fails.
If it fails, note what part of your recommendation changes.

### Math to physical link
Show one equation-to-physical-system connection.
Do not just show math; explain what physical behavior it represents.

### Skeptical challenge
Name the first point a skeptical engineer would challenge.
State what additional evidence would resolve that challenge.

## Copy-ready template
```markdown
# Warrant Entry

## Belief update
What I believed before this session that I now revise:
What changed it:

## Assumption + failure condition
Assumption:
Failure condition:
Impact on recommendation if failure occurs:

## Math to physical link
Equation/result:
Physical behavior it represents:

## Skeptical challenge
Likely challenge:
Evidence needed to resolve it:
```

## Short example entry
- **Belief update:** I assumed conversion yield was the dominant risk, but utility duty now appears dominant after weekly energy-balance checks.
- **Assumption + failure condition:** I assumed stable feed composition; this fails if feed variability exceeds the last calibration window and would shift control priority.
- **Math to physical link:** The duty estimate increased with higher reflux ratio, matching the observed rise in condenser load.
- **Skeptical challenge:** A reviewer would challenge whether this recommendation holds under off-design feed; I need one sensitivity run.

## Pair with
- [Good Questions](prompts/good-questions.md)
- [Evidence Check](prompts/evidence-check.md)
- [Reasoning Rubric](rubrics/reasoning-rubric.md)

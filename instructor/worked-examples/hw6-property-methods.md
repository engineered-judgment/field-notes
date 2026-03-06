# HW6 - Properties and Ternary Analysis

**Course:** CBE 253 - Aspen Plus Module  
**Sessions:** 9-12 - Weeks 14-15 - Apr 21 - Apr 30  
**Assignment:** HW6 - Property Analysis: n-Pentane/Methanol/Acetone System  
**Due:** May 5  
**Primary Mindset:** Decision  
**Connection forward:** This is the final entry. The property method question planted in HW1 - what does IDEAL cost you for a hydrogen-bonding system? - has a quantitative answer now. The T-xy diagrams you generated this week are the evidence. Every simulation in this course used a property method someone chose. This week you learned what that choice means.

---

## Simulation Context

**Problem 1 - Binary analysis.** n-Pentane/methanol system at 100 psia. T-xy diagrams and Gibbs free energy of mixing plots generated using three property methods: van Laar, Peng-Robinson, and UNIQUAC. Analysis of azeotrope prediction and two-liquid-phase behavior from Delta Gmix plots at 77 F.

**Problem 2 - Ternary analysis.** n-Pentane/methanol/acetone system at 100 psia using UNIQUAC. Ternary phase diagram generated to assess miscibility for each component pair, azeotrope locations, and phase behavior at overall composition 0.4 pentane / 0.4 methanol / 0.2 acetone.

---

## The Entry

### 01 - Belief Update `DECISION`

I assumed that different property methods would give similar T-xy diagrams for the same system - that the choice of method was a refinement, not a fundamental change in what the simulation predicts. After generating T-xy diagrams for n-pentane/methanol with van Laar, Peng-Robinson, and UNIQUAC, I no longer believe that. The three diagrams are qualitatively different. Peng-Robinson, an equation of state designed for nonpolar systems, does not predict the azeotrope that van Laar and UNIQUAC show for this polar-nonpolar pair. The property method is not a refinement - it is a modeling assumption that determines what phenomena the simulation can see. A simulation using Peng-Robinson for pentane-methanol is blind to the azeotrope. It will converge, produce output, and report nothing unusual - because the model cannot represent the non-ideal liquid behavior that creates the azeotrope.

> **Annotation:** This is the belief update the entire course has been building toward. From HW1, where IDEAL was accepted without question, to this week, where three methods produce qualitatively different results for the same system. The student has arrived at the central lesson of property method selection: the choice determines what physics the model can represent, not just how accurately it represents it. A model that cannot represent an azeotrope will not predict one regardless of how carefully the simulation is set up. This understanding is prerequisite to any serious process simulation work.

---

### 02 - Assumption + Failure Condition `DECISION`

I assumed UNIQUAC is the most accurate of the three methods for this system because it accounts for molecular size and surface area differences - pentane and methanol are very different in both. This assumption is reasonable and supported by the decision tree in the course notes: for polar non-electrolyte systems at low to moderate pressure where liquid-liquid equilibrium may occur, activity coefficient models like UNIQUAC are preferred over equations of state. It fails if binary interaction parameters for pentane-methanol are not available in the Aspen database or were regressed from data outside the temperature and pressure range of this simulation. UNIQUAC with poorly fitted parameters can perform worse than a simpler model with well-fitted ones. I accepted the Aspen database parameters without verifying their source or regression range.

> **Annotation:** The student made a specific property method recommendation - UNIQUAC - and immediately identified its failure condition: parameter quality. This is the Decision mindset made operational. Recommending a property method is not just choosing from a decision tree; it is accepting responsibility for the parameters that implement the model. The honest admission that database parameters were accepted without verification is not a weakness in the entry - it is the correct statement of what was done and what was not. In professional practice, parameter verification is a required step before a simulation is used for design decisions.

---

### 03 - Math to Physical Link `DECISION`

The Gibbs free energy of mixing plot for pentane-methanol at 77 F connected thermodynamic theory to a visible prediction. A negative Delta Gmix across the full composition range means the components mix spontaneously - one liquid phase. A Delta Gmix curve with a positive region or an inflection point indicating local concavity signals the possibility of two liquid phases. For pentane-methanol at 77 F, UNIQUAC showed a Delta Gmix curve with the characteristic double-well shape - two minima separated by a local maximum - indicating that compositions in the middle range would spontaneously split into two liquid phases of different compositions. Van Laar predicted a similar shape. Peng-Robinson did not - its Delta Gmix curve was negative and concave throughout, missing the liquid-liquid behavior entirely. The mathematics of the mixing curve directly predicted a physical phenomenon visible in the ternary diagram.

> **Annotation:** The connection between Delta Gmix curve shape and liquid-liquid phase splitting is the most important mathematical link in this assignment. A student who can look at a Delta Gmix plot and read two liquid phases from the double-well shape has internalized the thermodynamic criterion for phase splitting - not as a formula to apply but as a visual pattern with a physical meaning. The observation that Peng-Robinson missed this behavior entirely closes the loop from Field 01: the method that cannot represent the non-ideal liquid behavior also cannot produce the Delta Gmix shape that signals it. The two observations confirm each other.

---

### 04 - Skeptical Challenge `DECISION`

A skeptical engineer would challenge my recommendation of UNIQUAC by asking for experimental data to validate it. I generated three T-xy diagrams that disagree with each other and selected UNIQUAC as most accurate based on theoretical reasoning - molecular size differences, suitability for polar systems, decision tree guidance. But I did not compare any of the three predictions against experimental VLE data for pentane-methanol. The NIST database contains experimental binary VLE data for this system. A recommendation of UNIQUAC that has not been checked against experiment is a theoretical preference, not a validated choice. In a design context - sizing a distillation column, predicting azeotrope composition - the difference between a validated and unvalidated property method choice can be the difference between a column that meets specification and one that does not.

> **Annotation:** The skeptical challenge names the missing step that converts a reasonable choice into a defensible one: experimental validation. This is the highest-level engineering judgment in the course - not selecting from a decision tree, but knowing what it would take to trust the selection. The NIST database is specifically mentioned because it is available in Aspen and was introduced in the lecture material. A student who knows it exists and knows it was not consulted has correctly identified the gap between what they did and what professional practice requires.

---

### Primary Mindset: DECISION

*Every simulation in this course used a property method. In the early weeks that choice was given - IDEAL, UNIFAC, SRK, STEAMNBS. This week the choice was yours to make and defend. The decision is not which method appears highest on a ranking - it is which method best represents the physics of the system you are modeling, with parameters you can verify, for conditions within the range where the model was validated. That is a different kind of question than anything Aspen can answer for you.*

---

## One-Paragraph Contrast

A weak entry reads: *"I generated T-xy diagrams using three property methods and they looked different. I chose UNIQUAC because it is more accurate for polar systems. The ternary diagram showed some two-phase regions. A skeptical engineer might question whether I chose the right property method."* That entry reports that the diagrams differed without naming how or why. It recommends UNIQUAC without connecting the recommendation to molecular reasoning or the Delta Gmix evidence. It notes two-phase regions on the ternary diagram without connecting them to the Delta Gmix analysis from Problem 1. And it produces a skeptical challenge that is indistinguishable from a question the student already answered - without naming experimental validation as the missing step. The plots were generated. The decision was not made.

---

## What This Entry Sets Up

This is the last entry. Look back at HW1 - the IDEAL property method for methanol-water, accepted without question because the assignment specified it. You now know what that acceptance cost: IDEAL cannot predict the non-ideal mixing behavior of a hydrogen-bonding system, would miss an azeotrope if one existed, and produces outlet temperatures that are wrong in a direction you could not quantify at the time. You can quantify it now. The six entries in this notebook trace a single arc: from accepting model assumptions silently to naming them, testing them, and defending the choices you make under uncertainty. That arc is what engineered judgment looks like in practice.

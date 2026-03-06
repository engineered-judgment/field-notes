# HW5 - Reactor and Distillation

**Course:** CBE 253 - Aspen Plus Module  
**Sessions:** 7-8 - Week 13 - Apr 14-16  
**Assignment:** HW5 - Ethylbenzene Dehydrogenation with RSTOIC and RADFRAC  
**Due:** April 21  
**Primary Mindset:** Systems  
**Connection forward:** The single-pass conversion calculated here - and the unreacted ethylbenzene leaving in the overhead - is the natural entry point for thinking about recycle streams and process economics. In a real styrene plant, that overhead is not waste, it is a recycle. HW6 begins to give you the property analysis tools to evaluate what separating and recycling it would cost.

---

## Simulation Context

Pure ethylbenzene feed (100 lbmol/hr, 370 F, 55 psia) enters an RSTOIC reactor at 1100 F and 50 psia. Two reactions in series: dehydrogenation of ethylbenzene to styrene (0.60 fractional conversion), followed by further dehydrogenation of styrene to toluene and methane (0.34 fractional conversion of styrene). Reactor effluent is cooled to 185 F at 37 psia in a HEATER block, then fed to an adiabatic FLASH2 unit at 32 psia that removes most H2 and CH4 as vapor. The liquid product feeds a RADFRAC column with partial vapor condenser, 25 psia condenser pressure, ~0.1 psi/stage pressure drop. RADFRAC inputs seeded from HW4 DSTWU results. Target: >=99.8 mol% styrene in bottoms. Property method: SRK.

---

## The Entry

### 01 - Belief Update `SYSTEMS`

I assumed the two reactions in the reactor were independent - that I could think about the ethylbenzene conversion and the styrene conversion separately and add the results. After setting up the RStoic block with "reactions in series" checked and watching how the second reaction consumed the styrene produced by the first, I no longer believe that. The second reaction cannot proceed until the first has produced styrene - the output of reaction one is the input to reaction two. The 0.34 fractional conversion of styrene applies to the styrene present after reaction one, not to the original feed. A student who treats the reactions as independent will calculate the wrong styrene yield and the wrong feed composition to the distillation column, which propagates error through the entire flowsheet.

> **Annotation:** The belief update identifies a sequencing error that is easy to make and consequential when made. The "reactions in series" checkbox in RStoic is not a formality - it changes the calculation. A student who understood why it changes the calculation has understood that process flowsheets are not collections of independent units but sequences where upstream outputs become downstream inputs. That is the Systems mindset precisely: the flowsheet as a connected whole, not a set of blocks.

---

### 02 - Assumption + Failure Condition `SYSTEMS`

I assumed that the HEATER block cooling the reactor effluent to 185 F at 37 psia would condense enough of the mixture that the subsequent FLASH2 unit would cleanly separate H2 and CH4 from the heavier hydrocarbons. This assumption holds when H2 and CH4 are the only light components - both have boiling points far below 185 F and will remain in the vapor phase. It fails if significant amounts of lighter cracking products form in the reactor at 1100 F - benzene, for instance, is more volatile than toluene and could partially report to the vapor stream from the flash unit along with H2 and CH4, reducing the liquid feed to the distillation column and changing its composition. The RStoic block does not model side reactions unless explicitly specified, so any cracking at 1100 F is invisible in this simulation.

> **Annotation:** The student has identified a real limitation of RStoic - it only models the reactions you tell it about. At 1100 F, ethylbenzene dehydrogenation is accompanied by thermal cracking reactions in real industrial reactors. The simulation is clean because unspecified reactions do not exist in RStoic. A student who recognizes that reactor temperature creates the possibility of side reactions the model ignores is thinking about the gap between the simulation and the physical system - which is the correct posture for every reactor simulation.

---

### 03 - Math to Physical Link `SYSTEMS`

The single-pass conversion of ethylbenzene - moles reacted divided by moles fed - connects the reactor output directly to the distillation column design. At 0.60 fractional conversion of ethylbenzene in reaction one, 40 lbmol/hr of unreacted ethylbenzene leaves the reactor alongside the styrene product. That unreacted ethylbenzene reports predominantly to the RADFRAC overhead because ethylbenzene is more volatile than styrene - it is the light key in the distillation. The overhead stream is therefore not pure product; it is mostly ethylbenzene with some toluene and trace methane. The bottoms is the styrene product. The column is not purifying a product - it is separating an unreacted reactant from a product, which is the most common distillation task in continuous chemical manufacturing.

> **Annotation:** The student has connected the reactor conversion number to the distillation column function. This is the Systems connection the assignment is designed to produce - the reactor and the distillation column are not two separate exercises, they are two stages of one process. The observation that the overhead is mostly unreacted ethylbenzene rather than a byproduct is physically correct and sets up the natural next question: where does that ethylbenzene go in a real plant? The answer is recycle, which is the topic that connects this course to reactor design and process economics.

---

### 04 - Skeptical Challenge `TRADEOFF`

A skeptical engineer would challenge the 99.8 mol% styrene specification and ask what it costs in reboiler and condenser duty to achieve it compared to, say, 99.0 mol%. The RADFRAC simulation converged to the specification, but getting there required adjusting the reflux ratio upward from the DSTWU estimate. Every increment of purity beyond 99.0% requires disproportionately more energy - the separation becomes harder as the light key concentration in the bottoms approaches zero. The condenser and reboiler duties at 99.8% purity are significantly higher than at 99.0%, and the specification of 99.8% was given without justification. A skeptical engineer would want to know what downstream process requires 99.8% rather than 99.0%, because the energy cost difference is real and the specification may be conservative.

> **Annotation:** The skeptical challenge questions the specification itself, not the simulation that achieved it. This is the correct target - specifications in engineering are not arbitrary, they exist because a downstream user or process requires a particular purity. A student who asks "why 99.8% and not 99.0%?" is thinking about the process in its industrial context. The observation that purity specifications become disproportionately expensive near 100% is thermodynamically correct and practically important - it is one of the reasons industrial distillation columns are designed to specification rather than to maximum achievable purity.

---

### Primary Mindset: SYSTEMS

*The reactor conversion sets the distillation feed composition. The distillation feed composition sets the reflux ratio and stage count needed to meet the purity specification. The purity specification determines the condenser and reboiler duties. Each unit in the flowsheet is a constraint on every unit downstream. Changing the reactor conversion by 10% changes the distillation column design. The flowsheet is a system - pulling one variable changes everything connected to it.*

---

## One-Paragraph Contrast

A weak entry reads: *"I simulated the reactor and distillation column in Aspen. The RStoic block modeled two reactions and the RADFRAC column separated the products. The bottoms product met the 99.8 mol% styrene specification. A skeptical engineer might question whether my column design is optimal."* That entry describes what blocks were used without recording what the student understood about how they interact. The reactions-in-series dependency goes unnoticed. The HEATER block assumption is accepted without examination. The single-pass conversion is reported as a number without connecting it to the distillation column feed composition. The purity specification is accepted without questioning why it was set there. The simulation was completed. The system was not understood.

---

## What This Entry Sets Up

The unreacted ethylbenzene in the overhead stream is a planted question about recycle. In a real styrene plant, that stream is recycled to the reactor feed - the process operates with recycle to improve overall yield. HW6 gives you the property analysis tools to begin characterizing the thermodynamic behavior of these component pairs. A student who understands that the overhead stream is mostly unreacted ethylbenzene will look at the ternary diagram in HW6 with a specific question: how does styrene, ethylbenzene, and toluene separate, and what does that mean for recycle design?

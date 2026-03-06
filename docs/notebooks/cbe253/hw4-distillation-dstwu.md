# HW4 - Distillation DSTWU

**Course:** CBE 253 - Aspen Plus Module  
**Sessions:** 5-6 - Weeks 12-13 - Apr 7-9  
**Assignment:** HW4 - Distillation of Styrene / Ethylbenzene / Toluene using DSTWU  
**Due:** April 21  
**Primary Mindset:** Approximation  
**Connection forward:** The DSTWU outputs recorded here become the starting inputs for the RADFRAC simulation in HW5. Where this entry ends - with an estimate and its known limitations - HW5 begins.

---

## Simulation Context

A reactor output mixture of 35 mol% styrene, 45 mol% ethylbenzene, and 20 mol% toluene is fed to a distillation column at 120 lbmol/hr, 310 F, 30 psia. The goal is to produce a high-purity styrene bottoms product (>=0.995 mol fraction) and an ethylbenzene-rich overhead (>=98.5% ethylbenzene recovery). DSTWU shortcut method, SRK property method. Total condenser, column top pressure 24 psia.

Design heuristics applied:

- Actual reflux ratio = 1.2-1.5 x minimum reflux ratio
- Actual equilibrium stages ~= 2 x minimum stages

---

## The Entry

### 01 - Belief Update `APPROXIMATION`

I assumed the heuristics - 1.2-1.5x minimum reflux ratio, twice the minimum stages - were rules with a physical basis that would reliably produce an optimal design. After working through the DSTWU iterations I no longer believe that. The heuristics encode *economic* experience from an era of specific energy costs and construction norms, not thermodynamic principles. At different energy prices or with different feed compositions the optimal point shifts. DSTWU showed me that when I set the reflux ratio to 1.2x minimum, the required stages increased significantly - and when I pushed toward 1.5x, the stage count dropped but energy cost went up. The heuristic range is a search window, not an answer. I picked a point inside that window based on the RR-versus-stages plot, not because any single point was provably optimal.

> **Annotation:** This is the belief update the assignment is designed to produce. The student arrived thinking heuristics are laws and left understanding they are compressed historical judgment. The specific observation - that 1.2x and 1.5x bound a tradeoff rather than prescribe a solution - shows the student actually ran the sensitivity and watched the curve, rather than picking a number and stopping. That is the Approximation mindset made explicit: every heuristic encodes assumptions about context that may not hold.

---

### 02 - Assumption + Failure Condition `APPROXIMATION`

I assumed SRK is appropriate for this styrene/ethylbenzene/toluene system. This assumption is reasonable - all three are nonpolar hydrocarbons and SRK handles nonpolar systems well - but it fails if small amounts of water or oxygenated species are present in the feed, as can happen in real dehydrogenation reactor effluents. SRK does not handle polar-nonpolar interactions accurately. In this simulation the feed is specified as pure hydrocarbon, so the assumption holds. In a real plant the feed would need to be characterized more carefully before accepting SRK as the property method.

> **Annotation:** The student correctly validated the property method choice for the specified system, then located precisely where it would fail in a real application. This is the right structure for an assumption check: confirm it holds now, identify the condition under which it doesn't. The connection to real reactor effluents is not a digression - it is the signal that the student is thinking about the simulation as a model of something physical, not as an exercise in itself.

---

### 03 - Math to Physical Link `SYSTEMS`

The Fenske equation underlies the minimum stages calculation in DSTWU - it assumes total reflux and constant relative volatility. At total reflux, every molecule that goes up comes back down, so the separation per stage is maximized. The minimum number of stages DSTWU reported (approximately 11 for this system) is therefore a lower bound that can never be achieved in practice, because real operation requires a finite distillate flow. The actual stages (approximately 22, following the 2x heuristic) account for the real reflux ratio. What connected for me: the temperature difference between the distillate (~290 F) and the bottoms (~340 F) maps directly to the volatility difference between ethylbenzene and styrene - styrene's higher boiling point (293 F versus 277 F for ethylbenzene) is what drives the separation and sets the reboiler temperature.

> **Annotation:** Two connections are made here and both are legitimate. The Fenske equation link is conceptual - minimum stages as a limit, not an operating point. The temperature-to-volatility link is observable - the student read the stream table and traced the number back to a physical property. The boiling point values are approximately correct for atmospheric pressure; the student is doing order-of-magnitude reasoning, which is appropriate at this stage. The column operating between those temperatures is not arbitrary - it is set by the thermodynamics of the system.

---

### 04 - Skeptical Challenge `TRADEOFF`

A skeptical engineer would challenge whether 0.995 mol fraction styrene in the bottoms is actually achievable at the reflux ratio and stage count I selected, and would ask to see the stream table, not just the block report. DSTWU is a shortcut - it estimates the operating conditions that *should* achieve the spec, but it does not verify that they do. The block report gives minimum stages and reflux ratio under idealized assumptions. Whether those translate to the specified purity in a rigorous tray-by-tray calculation is not confirmed until RADFRAC is run. I am reporting a design estimate, not a verified result. The skeptical engineer would be right to want the RADFRAC confirmation before signing off on the column design.

> **Annotation:** The student has correctly identified the epistemological status of DSTWU output: it is an estimate whose validity is contingent on the rigorous calculation agreeing with it. DSTWU is a tool for getting to RADFRAC, not a substitute for it. A student who understands this is ready for HW5. A student who treats DSTWU output as the final answer will be confused when RADFRAC gives different results.

---

### Primary Mindset: APPROXIMATION

*Every number DSTWU reports is conditional on assumptions that RADFRAC will test. The minimum stages, the optimal reflux ratio, the distillate-to-feed ratio - all are estimates derived from simplified thermodynamic assumptions (constant relative volatility, constant molar overflow). Recording which assumptions were made and where they are likely to hold is the intellectual work of this assignment.*

---

## One-Paragraph Contrast

A weak entry for this assignment reads: *"I used DSTWU to find the number of stages and reflux ratio. I set the reflux ratio to 1.3 times the minimum and the stages to twice the minimum as the heuristic says. The block report showed the required values and the design criteria were met."* That entry reports procedure without recording judgment. It does not name what the heuristic encodes, does not question whether SRK is appropriate, does not connect the temperature profile to the volatility difference, and does not flag that DSTWU results are estimates awaiting RADFRAC confirmation. The simulation was run correctly. The thinking is invisible.

---

## What This Entry Sets Up

The DSTWU outputs from this entry - approximately 22 actual stages, reflux ratio in the 1.3-1.4x minimum range, distillate-to-feed ratio near 0.55, feed stage near the middle of the column - become the starting inputs for RADFRAC in HW5. The skeptical challenge in Field 04 is not rhetorical: it is the literal setup for the next assignment. When RADFRAC disagrees with DSTWU, the student who wrote this entry will have already predicted that disagreement and will be able to explain why it happened rather than treating it as an error.

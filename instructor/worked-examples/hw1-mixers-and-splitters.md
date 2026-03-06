# HW1 - Mixers and Splitters

**Course:** CBE 253 - Aspen Plus Module  
**Sessions:** 1-3 - Weeks 10-11 - Mar 24 - Mar 31  
**Assignment:** HW1 - Methanol Stream Separation and Mixing  
**Due:** March 31  
**Primary Mindset:** Constraint  
**Connection forward:** The IDEAL property method used here for methanol-water is a planted question. HW6 will generate T-xy diagrams for this same system using NRTL and Wilson - and the diagram will look nothing like what IDEAL predicts. The error you accepted here becomes the lesson there.

---

## Simulation Context

A high-purity aqueous methanol feed (98.5 mol% methanol, 150 lbm/hr, 130 F, 25 psia) is split using an FSPLIT block: 40 wt% routes to Mixer M200 where it combines with 30 kg/hr water at 15 C and 1 atm to form Product A; the remaining 60 wt% routes to Mixer M100 where it combines with 15 kg/hr water at 70 F and 1 atm to form Product B. Both mixers operate at 1 atm. Property method: IDEAL.

---

## The Entry

### 01 - Belief Update `CONSTRAINT`

I assumed that choosing IDEAL as a property method was a neutral starting point - a safe default that would give approximate answers without introducing meaningful error. After running the simulation and verifying the energy balance by hand, I no longer believe that. IDEAL assumes liquid activity coefficients of 1.0 for all components - it treats methanol and water as if they mix without any excess enthalpy, as if the molecules have no preference for their neighbors. Methanol and water are both strongly hydrogen-bonding molecules. They do not mix ideally. The product temperatures and compositions Aspen reported are approximations whose error I have not quantified, and the assignment did not ask me to.

> **Annotation:** Most students accept IDEAL without question because the simulation converges cleanly and the output looks reasonable. The student who records this belief update is asking the right question - not "did it converge?" but "what physical claim did I accept when I made that choice?" The payoff is deferred to HW6, where applying NRTL or Wilson to methanol-water produces a T-xy diagram that looks substantially different from IDEAL. A student who wrote this entry will recognize that difference immediately and be able to explain it. A student who did not will be surprised.

---

### 02 - Assumption + Failure Condition `CONSTRAINT`

I assumed the FSPLIT block correctly routes 40 wt% of the feed to M200 and 60 wt% to M100 based on the split fraction I specified. This assumption holds as long as the split fraction is specified on a mass basis and the feed composition is constant. It fails if the feed composition changes - FSPLIT applies the same split fraction regardless of composition, so a feed with a different methanol-to-water ratio would still split 40/60 by weight but would produce products with different compositions than expected. In a real plant where feed composition varies, an FSPLIT block would need to be paired with a controller or replaced with a more sophisticated splitting model.

> **Annotation:** The student has identified a real limitation of FSPLIT that the homework does not surface - it is a fixed-fraction splitter, not a composition-controlled splitter. The failure condition is specific and realistic: feed composition variation is common in real processes. This is the Constraint mindset applied correctly - the model works within its stated assumptions, and the student has named where those assumptions end.

---

### 03 - Math to Physical Link `CONSTRAINT`

The energy balance verification - comparing total inlet enthalpy to total outlet enthalpy for each mixer - connected the abstract conservation equation to a physical observable. In M100, the methanol-rich stream at 130 F mixes with cooler water at 70 F. The outlet temperature I calculated by hand from the enthalpy balance agreed with Aspen's output to within rounding. What this confirmed: Aspen is solving the same enthalpy balance I would solve by hand, just with property data pulled from the IDEAL model rather than steam tables or a handbook. The simulation is not doing something mysterious - it is doing arithmetic I can check.

> **Annotation:** The energy balance check is Question 3 in the homework, so most students complete it. Fewer connect it to what the check actually demonstrates - that the simulator is solving the same equations the student knows, with the same conservation laws, just faster and with more components. A student who understands this is positioned to diagnose convergence errors later in the course, because they know what Aspen is trying to do and can recognize when it fails to do it.

---

### 04 - Skeptical Challenge `CONSTRAINT`

A skeptical engineer would ask whether the product temperatures reported are physically meaningful given the IDEAL property method assumption. For a methanol-water system, mixing enthalpy is not zero - there is a measurable heat of mixing that IDEAL ignores. The outlet temperatures Aspen reported are therefore slightly wrong in a direction that depends on the actual excess enthalpy of mixing at these compositions. I cannot quantify the error without a better property model, but I know the error exists and that it affects the temperature more than the composition - because compositions are set by the mass balance, which is property-method-independent.

> **Annotation:** The student has made a precise and correct observation: the mass balance is property-method-independent (mass is conserved regardless of thermodynamic model), but the energy balance is not (enthalpy depends on the model). Naming the direction and type of error without knowing the magnitude is honest and technically correct. This is what engineering judgment under uncertainty looks like - not refusing to answer, but answering with explicitly stated limitations.

---

### Primary Mindset: CONSTRAINT

*The IDEAL property method is not a neutral choice - it is a constraint that bounds the validity of every temperature Aspen reported. The FSPLIT split fraction is not a physical law - it holds only when feed composition is constant. Naming the constraints you accepted, and the conditions under which they fail, is the intellectual work of this week.*

---

## One-Paragraph Contrast

A weak entry reads: *"I learned how to use the mixer and splitter blocks in Aspen Plus. I used the IDEAL property method as specified. The energy balance confirmed conservation of energy. A skeptical engineer might question whether my results are accurate."* That entry accepts IDEAL without examining what it assumes, reports the energy balance as a confirmation without connecting it to what was actually being confirmed, and produces a skeptical challenge so broad it applies to every simulation ever run. The blocks were placed correctly. The streams were connected. The simulation converged. The thinking is absent.

---

## What This Entry Sets Up

The IDEAL property method for methanol-water is an open question that HW6 closes. When you generate the T-xy diagram for methanol-water using NRTL in HW6, the curve will show non-ideal behavior that IDEAL cannot predict. A student who wrote this entry will look at that diagram and immediately understand why it differs. A student who accepted IDEAL without question will have no framework for the difference and may assume the NRTL result is wrong rather than recognizing it as more accurate.

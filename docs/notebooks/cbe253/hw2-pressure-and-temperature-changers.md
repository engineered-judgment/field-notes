# HW2 - Rankine Cycle

**Course:** CBE 253 - Aspen Plus Module  
**Sessions:** 1-3 - Weeks 10-11 - Mar 24 - Mar 31  
**Assignment:** HW2 - Steam Rankine Cycle  
**Due:** March 31  
**Primary Mindset:** Tradeoff  
**Connection forward:** The cycle efficiency number calculated here is a permanent reference point. Every heat integration scheme, combined cycle configuration, or process improvement you encounter later in your engineering career will be evaluated against a baseline. You just calculated yours.

---

## Simulation Context

4171 kg/hr of saturated liquid water at 0.025 MPa is pumped to 0.8 MPa (pump efficiency 0.8, driver efficiency 0.9), fed to a boiler producing superheated steam at 500 C, expanded through an isentropic turbine back to 0.025 MPa (isentropic efficiency 0.9, mechanical efficiency 0.9), then condensed to saturated liquid completing the cycle. Blocks: PUMP (P100), HEATER for boiler (H100), COMPR for turbine (C100), HEATER for condenser (H200). Property method: STEAMNBS.

---

## The Entry

### 01 - Belief Update `TRADEOFF`

I assumed the pump and turbine were symmetric opposites - one puts work in, one takes work out, and they cancel in a straightforward way. After computing the cycle efficiency by hand, I no longer believe that. The pump work is small - roughly 1-2% of what the turbine produces at these conditions. The asymmetry exists because liquids are nearly incompressible: pumping a liquid to high pressure requires very little work compared to expanding a vapor through the same pressure drop. The turbine produces far more work than the pump consumes precisely because the working fluid changes phase between the two. That phase change is not incidental to the Rankine cycle - it is the entire reason the cycle is efficient. Removing it would collapse the work advantage.

> **Annotation:** The belief update identifies the physical mechanism behind a numerical result - the pump-turbine work asymmetry is not arbitrary, it follows directly from the incompressibility of liquids versus the expansibility of vapors. A student who understands this can immediately explain why gas turbine cycles, which compress a gas rather than pump a liquid, have lower theoretical efficiency than steam cycles for the same temperature ratio. That comparison is not in the homework but it is the natural next question for a student who has genuinely understood the Rankine cycle rather than just calculated its efficiency.

---

### 02 - Assumption + Failure Condition `TRADEOFF`

I assumed the specified pump and turbine efficiencies (0.8 pump isentropic, 0.9 turbine isentropic) represent realistic steady-state operating conditions. This assumption holds for a well-maintained plant operating near its design point at full load. It fails under partial load - when the turbine operates below capacity, isentropic efficiency drops, sometimes below 0.7 for large steam turbines at 50% load. The cycle efficiency I calculated is therefore an upper bound on what the plant achieves in real operation, where load varies continuously in response to grid demand. The condenser duty as a fraction of boiler input would be larger at partial load than my numbers suggest.

> **Annotation:** The partial load failure condition is not exotic - power plants cycle load constantly. A student who identifies this limitation is thinking about the simulation as a model of a real operating system with a load profile, not a textbook problem with a fixed operating point. The observation that condenser duty grows as a fraction of boiler input at partial load is thermodynamically correct and practically important - it affects the thermal discharge to whatever cooling medium the plant uses.

---

### 03 - Math to Physical Link `TRADEOFF`

The hand calculation for overall cycle efficiency - (Turbine Net Work - Pump Net Work) / Boiler Heat Duty - placed each Aspen output on the T-S diagram I already knew from thermodynamics. The boiler takes the stream from compressed liquid to superheated vapor: large enthalpy increase, large heat input, horizontal movement on the T-S diagram at constant pressure. The turbine extracts work by dropping enthalpy along a nearly isentropic path: vertical drop on the T-S diagram. The condenser rejects everything that was not converted to work - the remaining enthalpy leaves as heat at low temperature and low pressure. The numbers confirmed the diagram. Nothing Aspen reported was surprising once I placed each stream on the cycle.

> **Annotation:** The T-S diagram connection is the most important link in this entry. Students who complete the efficiency calculation without placing streams on the diagram are doing arithmetic without physical grounding. A student who can place each Aspen stream result on the T-S diagram - compressed liquid, superheated steam, wet vapor after expansion, saturated liquid after condensation - has integrated the simulation output with thermodynamic knowledge they already possessed. That integration is what Field 03 is designed to capture.

---

### 04 - Skeptical Challenge `TRADEOFF`

A skeptical engineer would challenge the thermal efficiency calculation and ask what happens to the energy the cycle rejects. The boiler inputs a large heat duty. The turbine extracts work. The condenser rejects everything not converted - and that heat goes somewhere: a river, a cooling tower, or the atmosphere. The simulation reports condenser duty as a number but does not model where that heat goes or what constraint governs its rejection. In a real plant sited near a water body, condenser duty determines the thermal discharge to the water, which is regulated under environmental permits. The efficiency I calculated is thermodynamically correct but environmentally incomplete - the condenser duty is not just a residual, it is a design constraint with regulatory consequences.

> **Annotation:** The skeptical challenge goes outside the simulation boundary deliberately. Condenser heat rejection is a real siting and permitting constraint - thermal discharge regulations have forced redesigns and shutdowns of real plants. A student who notices that the condenser duty in their Aspen output represents a real environmental constraint is beginning to think like a practicing engineer. The Tradeoff is explicit: cycle efficiency was maximized at the cost of a condenser duty that has to go somewhere, and where it goes is not the simulator's problem - it is the engineer's.

---

### Primary Mindset: TRADEOFF

*Every joule the boiler puts in either leaves as turbine work or leaves as condenser heat rejection. There is no third option. Increasing cycle efficiency means extracting more work from the same boiler input - which means reducing what the condenser rejects. The tradeoff between work output and heat rejection is not a design choice to be optimized away; it is a thermodynamic constraint. The Carnot limit exists for this reason.*

---

## One-Paragraph Contrast

A weak entry reads: *"I simulated the Rankine cycle in Aspen using a pump, boiler, turbine, and condenser. The cycle efficiency came out to about 30%. I assumed the efficiencies given were correct. A skeptical engineer might question the accuracy of my simulation."* That entry reports the efficiency number without connecting it to the T-S diagram, accepts the specified efficiencies without identifying where they fail, and produces a skeptical challenge that challenges nothing specific. The pump-turbine work asymmetry goes unnoticed. The condenser duty is a number, not a constraint. The simulation was completed. The cycle was not understood.

---

## What This Entry Sets Up

The Rankine cycle efficiency number is a permanent reference point - roughly 30% for these conditions, meaning roughly 70% of the boiler input leaves as condenser heat rejection. Any process improvement, heat integration scheme, or combined cycle configuration encountered later in your engineering career will be evaluated against a baseline like this one. The condenser duty concern raised in Field 04 connects directly to HW6 - where property method selection and thermodynamic analysis tools will give you the means to characterize real fluid behavior more precisely than STEAMNBS alone. The cycle you simulated here is ideal in its block structure; real plants are more complex, but this calculation is where your intuition for steam cycle performance begins.

Warrant
Comprehensive Worked Example
With Scaffolding Annotations and Rubric Calibration Notes


How to Use This Document
This document contains one complete Warrant entry, written for a flash separation simulation using an ethanol-water system. The simulation context is not drawn from any homework assignment in this course - it uses familiar block types (SEP, FLASH2, HEATER) applied to a different chemical system. This is deliberate: the scaffolding annotations explain the thinking process behind each field, not the content of any specific homework.

For Students
Read this document once before writing your first Warrant entry. Focus on the scaffolding annotations - the amber boxes - which explain how the student arrived at each field, not just what they wrote. The entry itself is a strong example of what specificity looks like. Read it, then close this document and write your own entry from your own simulation. Do not return to this document while writing.

For Instructors
The rubric calibration notes at the end of this document are the primary tool for developing and iterating the Warrant rubric over time. The strong and weak versions of each field, read alongside the calibration notes, define the boundaries between rubric levels. As you read student entries across the semester, return to this document to check your calibration - particularly for Field 01, where the boundary between a genuine belief update and a content summary is the most difficult judgment call.


Simulation Context
Ethanol-water flash separation. A feed stream of 100 lbmol/hr containing 30 mol% ethanol and 70 mol% water at 80 F and 14.7 psia enters a SEP block that routes 95% of the ethanol to one product stream. The remaining stream - mostly water with trace ethanol - enters a HEATER block that raises the temperature to 200 F at 14.7 psia before entering a FLASH2 unit operating at 14.7 psia with a duty specification of zero (adiabatic). Property method: IDEAL.

This simulation was chosen for the worked example because:
- It uses block types introduced early in the course - SEP, HEATER, FLASH2
- The IDEAL property method creates a genuine and detectable problem for a hydrogen-bonding system
- The SEP versus FLASH2 distinction is the central conceptual shift the entry demonstrates
- The ethanol-water system is familiar enough to be legible without Aspen knowledge


Before the Simulation
The following questions are given to students before they open Aspen. They are not graded. Their purpose is to prime the student to notice things worth recording - so that the simulation generates raw observations rather than just output.

PRE-SIMULATION PROMPT CARD
Answer in one sentence each. Do this before opening Aspen.
- What do you expect to happen to ethanol versus water when the stream flashes at 200 F and atmospheric pressure?
- Which block in this flowsheet is enforcing a split you chose, and which is calculating a split from thermodynamics?
- Ethanol and water are both strongly hydrogen-bonding. What does IDEAL assume about how they interact?
- If your simulation converges cleanly, does that confirm the property method is appropriate?

SCAFFOLDING ANNOTATION
These four questions map directly to the four Warrant fields. Q1 primes Field 01 - the student who has written a one-sentence prediction before running the simulation has something specific to compare against the output. Q2 primes Field 02 - the SEP versus FLASH2 distinction. Q3 and Q4 prime Fields 02 and 04 - the IDEAL assumption and its failure condition.

The most important question is Q4. A student who can answer 'no' before running the simulation - who already knows that convergence is not validation - is positioned to write a genuine Field 04 rather than a generic one. A student who answers 'yes' will have their assumption tested by the simulation and may produce a stronger Field 01 as a result.

Release this card at the start of the session. Collect the written answers on paper before students open Aspen. Do not grade them - but do read them quickly as students work. The answers tell you what the class expected before running. That gap between expectation and output is where the Warrant entry lives.


The Entry - Strong Version

Field 01 - Belief Update
01 - Belief Update   CONSTRAINT
I assumed the SEP block and the FLASH2 block were both separating streams - different tools for the same job. After running the simulation and looking at both outputs, I no longer believe that. The SEP block produced exactly the split I specified: 95% of the ethanol to one stream, regardless of whether that split is thermodynamically achievable at these conditions. The FLASH2 block produced a split I did not specify - it calculated what vapor and liquid phases form at 200 F and 14.7 psia based on the equilibrium thermodynamics of the system. These are fundamentally different operations. The SEP result can be physically impossible and the simulation will not tell me. The FLASH2 result is constrained by thermodynamics and will fail to converge if I ask for something the system cannot do.

SCAFFOLDING ANNOTATION
HOW THE STUDENT ARRIVED HERE: The pre-simulation prompt card asked which block enforces a split the student chose versus which calculates one from thermodynamics. A student who answered that question before running the simulation arrived at the output with a specific prediction to test. When the SEP block produced exactly 95% ethanol split regardless of conditions, and the FLASH2 block produced a vapor fraction the student did not specify, the contrast was visible.

WHAT MAKES THIS STRONG: The belief update names two specific things - what the student believed before (both blocks separate streams, different tools for the same job) and what changed it (SEP enforces, FLASH2 calculates, and these are fundamentally different). The last sentence is the strongest part: 'The SEP result can be physically impossible and the simulation will not tell me.' That sentence demonstrates the student understands the epistemological consequence of using SEP, not just its operational difference from FLASH2.

WHAT TO WATCH FOR IN STUDENT ENTRIES: A weak Field 01 summarizes content - 'I learned about the difference between SEP and FLASH2.' A strong Field 01 records a specific belief that changed and names what changed it. The test: can you identify what the student believed before, and what specific observation changed it?

Field 02 - Assumption + Failure Condition
02 - Assumption + Failure Condition   FRAGILITY
I assumed IDEAL is an acceptable property method for ethanol-water because the assignment specified it and the simulation converged without errors. This assumption fails for any calculation where the non-ideal mixing behavior of ethanol and water matters - specifically, phase equilibrium predictions near the known azeotrope at approximately 89 mol% ethanol at atmospheric pressure. IDEAL assumes activity coefficients of 1.0 for both components, which means it predicts vapor-liquid equilibrium as if the molecules had no preference for their neighbors. Ethanol and water interact strongly through hydrogen bonding - their activity coefficients are measurably greater than 1.0 across the full composition range. A FLASH2 simulation using IDEAL near the azeotrope composition would predict the wrong vapor fraction and the wrong product compositions. The simulation converged, but convergence confirmed that the calculation completed - not that the property method is appropriate.

SCAFFOLDING ANNOTATION
HOW THE STUDENT ARRIVED HERE: The pre-simulation prompt card asked what IDEAL assumes about how ethanol and water interact, and whether convergence confirms the property method is appropriate. A student who wrote 'no' to the second question before running arrived at the simulation already skeptical. The convergence without error did not reassure them - it confirmed the question.

WHAT MAKES THIS STRONG: Three elements are present. First, the assumption is named specifically - IDEAL, activity coefficients of 1.0, what that physically means. Second, the failure condition is located precisely - near the azeotrope composition, not generically 'when conditions change.' Third, the last sentence resolves the Q4 pre-simulation prompt explicitly: convergence confirmed the calculation completed, not that the method is appropriate. That sentence is doing real intellectual work.

THE FAILURE CONDITION TEST: Ask whether the failure condition named could apply to any simulation or only this one. 'If the system behaves differently than expected' fails the test. 'Near the azeotrope at 89 mol% ethanol at atmospheric pressure' passes it. The more specific the failure condition, the more certain you are the student engaged with this system rather than producing a generic answer.

NOTE ON AZEOTROPE: Ethanol-water forms a well-known homogeneous azeotrope at ~89 mol% ethanol, 78.2Ã‚ C at 1 atm. IDEAL cannot predict this - it predicts monotonic behavior. This is verifiable and the student would discover it in HW6 when generating T-xy diagrams with NRTL.

Field 03 - Math to Physical Link
03 - Math to Physical Link   SYSTEMS
The Rachford-Rice equation governs the flash calculation in FLASH2. At 200 F and 14.7 psia, the adiabatic flash produced approximately 35 mol% vapor. That vapor is enriched in ethanol relative to the feed - ethanol's normal boiling point (173 F) is lower than water's (212 F), so ethanol preferentially partitions to the vapor phase. The stream table confirmed this: the vapor product showed approximately 58 mol% ethanol versus 30 mol% in the feed entering the flash unit. The equation predicted a direction - lighter component goes to vapor - and the stream table confirmed the magnitude. What connected for me: the FLASH2 result is not a black box. It is solving the same phase equilibrium I would calculate by hand with K-values, just iterating to convergence faster than I could.

SCAFFOLDING ANNOTATION
HOW THE STUDENT ARRIVED HERE: The stream table is the source. A student who looks at the vapor product composition and compares it to the feed composition sees the enrichment directly. The connection to Rachford-Rice comes from asking 'what equation is Aspen solving here?' - which is the question Field 03 is designed to prompt.

WHAT MAKES THIS STRONG: The student names an equation (Rachford-Rice), connects it to a specific numerical output (35 mol% vapor, 58 mol% ethanol in vapor), and traces that number back to a physical property (boiling point difference). The last sentence - 'it is solving the same phase equilibrium I would calculate by hand with K-values' - is the most important line. It demystifies the simulation. A student who understands this will not be confused when FLASH2 fails to converge, because they know what convergence requires.

WHAT FIELD 03 IS REALLY ASKING: Not 'name an equation you used' but 'find the place where a mathematical relationship produced a physically observable result.' The numbers should come from the student's own stream table - which means they must have looked at it, not just run the simulation and moved on.

MINIMUM STANDARD: Field 03 must contain at least one specific number from the simulation output and one connection to a physical property or observable. An entry that names an equation without a number, or a number without a physical connection, is incomplete.

Field 04 - Skeptical Challenge
04 - Skeptical Challenge   TRADEOFF
A skeptical engineer would challenge the SEP block specification - 95% ethanol recovery - and ask for evidence that this split is achievable at these conditions. The SEP block will produce that split regardless of thermodynamics. But at 80 F and 14.7 psia, a 30 mol% ethanol feed is entirely liquid - there is no vapor phase to separate to. A real separation at these conditions would require a different mechanism entirely: distillation, liquid-liquid extraction, or adsorption. The SEP block hid this problem. If I had used a FLASH2 block instead of a SEP block for the first separation, Aspen would have told me that no vapor forms at these conditions - which is physically correct. I used SEP because it was computationally convenient. The skeptical engineer would be right to ask what physical equipment corresponds to that block.

SCAFFOLDING ANNOTATION
HOW THE STUDENT ARRIVED HERE: This requires the student to ask what physical equipment the SEP block represents. SEP is often described in courses as a 'black box separator' - which is accurate but conceals the question of whether the separation it performs is physically realizable. A student who asks 'what piece of equipment does this correspond to?' at 80 F and 14.7 psia discovers that the feed is entirely liquid, and a 95% ethanol split from an entirely liquid stream has no obvious physical mechanism.

WHAT MAKES THIS STRONG: The challenge is specific and self-critical. The student is not challenging a classmate's work or a generic simulation practice - they are identifying a problem in their own flowsheet and naming what it would have taken to catch it (using FLASH2 instead of SEP). This is the highest form of Field 04: a skeptical challenge that the student can substantiate and that points to a concrete alternative.

THE FIELD 04 TEST: The skeptical challenge must name something specific that would actually change the conclusion or require additional evidence. 'A skeptical engineer might question the accuracy of my results' fails the test - it applies to every simulation ever run. 'A skeptical engineer would ask what physical equipment corresponds to the SEP block at these conditions' passes it, because it identifies a specific gap and implies a specific check.

NOTE FOR INSTRUCTORS: Some students will write Field 04 as a question they already answered - 'a skeptical engineer might question whether IDEAL is appropriate, but I already addressed that in Field 02.' This is a sign that the student is treating Field 04 as redundant. Prompt them to find a challenge that goes outside the simulation boundary - something the model cannot address, not something the student already addressed.


The Entry - Weak Version
The following entry covers the same simulation. All four fields are present. The simulation was run correctly. The thinking is absent.

WEAK VERSION - 01 - Belief Update
I learned about the difference between the SEP block and the FLASH2 block. The SEP block separates based on specified fractions while the FLASH2 block uses phase equilibrium. I also learned that the IDEAL property method may not be the best choice for all systems. This was an interesting simulation that helped me understand separators better.

WHY THIS FAILS
This field summarizes course content rather than recording a belief that changed. 'I learned about the difference between SEP and FLASH2' is a content summary - it says the student now knows something they did not know before, but does not name what they believed before or what specific observation changed it. The last sentence ('this was an interesting simulation') is the weakest possible closing - it signals that the student has run out of things to say and is filling space.

The test: what did the student believe before this session that they no longer believe? That question cannot be answered from this entry. The field fails the basic definition of a belief update.

WEAK VERSION - 02 - Assumption + Failure Condition
I assumed the IDEAL property method was appropriate for this simulation. This assumption could fail if the system behaves differently than expected or if the conditions change significantly. The property method is important to choose correctly for accurate results.

WHY THIS FAILS
The assumption is named (IDEAL) but not examined. The failure condition - 'if the system behaves differently than expected' - applies to every simulation ever run. It contains no specific information about this system, these components, or these conditions. The closing sentence restates the general importance of property method selection without saying anything about why IDEAL specifically is problematic for ethanol-water.

The minimum requirement for Field 02: name the specific condition under which this assumption fails for this system. For IDEAL and ethanol-water, that condition is near the azeotrope composition. A student who cannot name the azeotrope did not engage with what IDEAL assumes or what ethanol-water actually does.

WEAK VERSION - 03 - Math to Physical Link
The flash calculation uses thermodynamic equations to determine the vapor and liquid compositions at the given conditions. The results showed that ethanol was enriched in the vapor phase because it is more volatile. The equations Aspen uses are based on phase equilibrium principles from thermodynamics.

WHY THIS FAILS
No equation is named. No number from the simulation appears. The observation that ethanol is enriched in the vapor phase is correct but generic - it follows from the boiling point difference without requiring the student to look at the stream table. 'The equations Aspen uses are based on phase equilibrium principles' is true of every flash calculation ever run - it contains no information specific to this simulation.

The minimum requirement for Field 03: one specific number from the simulation output, connected to one physical property or observable. Without numbers from the stream table, there is no evidence the student looked at the output rather than inferring the result from general knowledge.

WEAK VERSION - 04 - Skeptical Challenge
A skeptical engineer might question whether the IDEAL property method gives accurate results for this system. They might also question whether the simulation setup is correct. To address this, a better property method could be used in future simulations.

WHY THIS FAILS
The skeptical challenge names something the student already addressed in Field 02 - the IDEAL property method - without adding anything new. The second sentence ('they might also question whether the simulation setup is correct') is so broad it is meaningless. The closing sentence proposes a future action rather than identifying a specific gap in the current analysis.

A skeptical challenge that can be answered with 'I already addressed that' is not a challenge - it is a restatement. Field 04 should go somewhere the simulation cannot follow: the physical realizability of the SEP block, the energy accounting for the separation, the regulatory constraint on what happens to the product stream. Somewhere outside the boundary of what was modeled.


Rubric Calibration Notes
This section is instructor-facing. It is not distributed to students. Use it to calibrate your reading of student entries and to develop the Warrant rubric over time. The strong and weak versions above define the boundaries. The notes below explain what to look for at each criterion.

Criterion 1 - Specificity of Belief Update (Field 01)
The central question: can you identify what the student believed before this session and what specific observation changed it? If either element is missing, the entry fails this criterion regardless of length or sophistication of language.

Level	What it looks like	Common failure mode
Strong	Names prior belief, specific observation that changed it, and consequence of the change	No prior belief named - summary of content only
Adequate	Names prior belief and observation but not the consequence	Prior belief is too vague to be falsifiable
Weak	Names one element only - usually the new knowledge without the prior belief	Entry is a learning summary: 'I learned that X'
Missing	Field is blank, restates the simulation context, or is fewer than two sentences	Field is present but contains no belief content

Criterion 2 - Precision of Failure Condition (Field 02)
The test: does the failure condition named apply specifically to this system at these conditions, or could it apply to any simulation? Generic failure conditions ('if conditions change,' 'if the system behaves differently') score at the weak level regardless of how well the assumption is named.

Level	What it looks like	Common failure mode
Strong	Assumption named with physical basis; failure condition locates the specific regime or composition where it breaks	Failure condition is generic: 'if assumptions are violated'
Adequate	Assumption named; failure condition is a category rather than a specific condition	Assumption is named without physical basis - just the label
Weak	Assumption named but failure condition is generic or absent	Failure condition restates the assumption: 'fails if IDEAL is wrong'
Missing	Field blank or names a condition rather than an assumption with a failure condition	Student describes what they did rather than what they assumed

Criterion 3 - Quantitative Grounding (Field 03)
The minimum standard: at least one number from the student's stream table or block report, connected to a physical property or observable. An entry without numbers has no evidence the student examined their output. An entry with numbers but no physical connection is arithmetic without understanding.

Level	What it looks like	Common failure mode
Strong	Equation named; specific number from output; physical property or mechanism that explains the number; demystifies what Aspen is computing	Number present but no equation and no physical connection
Adequate	Number from output connected to a physical observation; equation may or may not be named	Equation named but number comes from general knowledge, not stream table
Weak	Number present but not connected to physical meaning, or connection made without a number	Result described qualitatively: 'ethanol was enriched in the vapor'
Missing	No numbers; field describes what flash calculations do in general	Student paraphrases lecture content rather than reporting simulation output

Criterion 4 - Specificity and Reach of Skeptical Challenge (Field 04)
Two tests apply. First: is the challenge specific to this simulation, or generic? Second: does the challenge go somewhere the simulation cannot follow - outside the model boundary - or does it only challenge what the student already addressed? The highest-scoring entries identify something the model omits entirely, not just something it approximates.

Level	What it looks like	Common failure mode
Strong	Specific challenge that goes outside the model boundary; names what evidence would be required; student can substantiate the challenge	Challenge restates Field 02 without adding new content
Adequate	Specific challenge within the model; names what would need to change for the conclusion to hold	Challenge is specific but already addressed elsewhere in the entry
Weak	Challenge is generic but not circular - applies to this class of simulations rather than all simulations	Challenge identifies a limitation without naming what it would take to address it
Missing	Challenge is completely generic ('a skeptical engineer might question my accuracy') or field is blank	Challenge is a question the student already answered in Fields 01-03

Rubric Iteration Guidance
After reading the first cohort of entries, return to these tables and note which level boundary is hardest to call consistently. The most common ambiguity is between Adequate and Weak in Field 01 - where the prior belief is named but too vague to be falsifiable. Updating the 'common failure mode' column with specific examples from student entries will improve inter-rater reliability if TAs are grading.

A second common ambiguity is in Field 04: entries that name the same limitation as Field 02 (property method concern) but frame it as a challenge rather than an assumption. These should score at the Adequate level - the content is not new but the framing shows the student understands that limitations have consequences. Reserve Strong for entries that genuinely go outside the model boundary.

Update this document at the end of each semester with two or three anonymized student entry excerpts at each rubric level. After two or three cohorts, the rubric tables will be calibrated against real student work rather than hypothetical descriptions.


Field Notes for Engineering  Ã‚-  engineered-judgment.github.io/field-notes

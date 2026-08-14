# Validation 0.5 — Final Design Refinements

Status: **Effective addendum to Phase 0 design**

This document records the latest design after three no-code paper walkthroughs and public reference desk validation.

If a Phase 0 document conflicts with this file, **this Validation 0.5 addendum wins** until the parent document is consolidated during implementation planning.

---

# 1. Harness Topology — CONFIRMED

No topology change.

Selected remains:

> **Stage-Gated Artifact Blackboard + Thin Director**

Reason:
- all three paper episodes required explicit rollback points
- source/claim/visual lineage remained important
- object/system scale varied, favoring artifact state over Director memory
- expensive visual production still benefits from hard previs gate

---

# 2. Core Physical Artifacts — SIMPLIFIED

Phase 0 defined 12 logical artifact types.

Validation result:
- keep the logical distinctions
- reduce Phase 1 default physical artifacts to **7**

Effective Phase 1 set:
1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Child artifacts are created only when complexity requires them.

---

# 3. Topic Brief → Episode Brief — EXPANDED

Required fields now include:
- central question
- episode grammar
- target audience
- X-Ray value
- **explanatory unit**: whole system / representative module / component
- **case anchor**: named real case if the visual story relies on one
- scope inclusions
- scope exclusions
- initial risk

Reason:
Roman aqueduct and undersea tunnel walkthroughs showed that a topic name alone leaves too much room for composite/generalized claims.

---

# 4. Hero Object Bible → Spatial / Asset Bible — RENAMED AND EXPANDED

`Hero Object` was too narrow for:
- aqueduct networks
- tunnel routes
- city water systems
- transport networks

Effective model:
- `hero_scope = object | system | component`

Spatial / Asset Bible owns:
- canonical structure/system
- axes/orientation
- component relationships
- hard/soft/free locks
- semantic anchors
- reconstructed/unknown regions
- scale treatment
- asset reuse

---

# 5. Continuity — FOUR CLASSES

Continuity QA must track:

## C-A Object Continuity
Same object/component remains structurally consistent.

## C-B Spatial Continuity
Orientation, axis, geography, section direction remain understandable.

## C-C Semantic Continuity
The viewer can follow the same water/force/person/signal/process across different representations.

Example:
map → elevation profile → 3D channel section must still feel like the same water journey.

## C-D Temporal Continuity
Era/state/build sequence remains coherent.

This replaces the narrower assumption that continuity means only consistent 3D geometry.

---

# 6. Scale Treatment — NEW VISUAL TRUTH FIELD

Every engineering explanatory shot can declare:
- TRUE_SCALE
- SCHEMATIC
- EXAGGERATED_FOR_EXPLANATION

Why:
- slopes/angles/layers can be invisible at true scale
- visual exaggeration is legitimate if declared and does not alter causal meaning
- fake precision risk must be controlled

This field belongs in Visual Plan and/or Spatial / Asset Bible.

---

# 7. 2D Diagram / Motion Graphics — FIRST-CLASS CAPABILITY

Previous visual design emphasized 3D and generative visuals.

Validation finding:
Some concepts are clearer in 2D first:
- elevation profile
- tiny angle error amplified over distance
- route map
- causal chain
- cross-section labels

Effective capability registry must include:
- technical diagram
- motion graphics
- map/elevation animation

These are not “cheap fallback visuals.” They are explanatory tools selected by objective.

---

# 8. Visual Method Selection Rule — REFINED

For each narration unit, choose the cheapest method that accurately proves the concept.

Candidate order is not strict, but available methods include:
- actual/reference image/footage
- 2D diagram
- map/elevation profile
- generated still
- generated video
- proxy/real geometry
- deterministic 3D render
- composited hybrid

Selection criteria:
1. explanatory fidelity
2. continuity
3. evidence truth
4. cost
5. aesthetics

Aesthetics is not criterion #1.

---

# 9. Reference Validation — PARTIAL, NOT OVERCLAIMED

Publicly observable title/script snippets support:
- familiar subject + hidden mechanism
- surprising physical constraint
- mechanism → new problem → engineered response
- numeric scale used as stakes

Still not verified here:
- exact frame grammar
- exact camera choreography
- exact production toolchain
- exact long-form pacing

Rule remains:
**do not infer tool names from visual appearance alone.**

---

# 10. Long-Form Direction — UNCHANGED

Even if a benchmark channel uses short-form heavily, Civilization X-Ray's selected product remains:
- long-form first
- 8–15 minutes default, topic-dependent
- short-form as derivative/discovery content later

Reason:
The project goal is to extend the explanatory grammar into a deeper, provenance-rich format, not to copy runtime.

---

# 11. Physical Agent Count — STILL UNDECIDED

Validation did not reveal a need to lock 14 separate agents.

Logical capabilities remain useful, but Phase 1 should start with the minimum physical agent/process count capable of respecting:
- independent claim verification
- script/editorial separation where needed
- spatial continuity review
- state/gate orchestration

Agent count is a runtime optimization, not a design goal.

---

# 12. Remaining No-Code Validation

Still valuable before implementation:
- actual frame+transcript corpus of 10 benchmark videos when direct media access is available
- use those findings to update visual action frequencies and camera grammar

This is **not a blocker to complete the architecture design**, because the harness supports grammar revision without topology changes.

---

# 13. Final Validation Verdict

## Strategic design
PASS

## Content system
PASS

## Script system
PASS

## Visual architecture
PASS with refinements above

## Risk / pre-mortem
PASS

## Harness architecture
PASS

## Artifact design
PASS after simplification to 7 core physical artifacts

## Reference frame-level empirical analysis
PARTIAL / pending direct media access

## Implementation
**NOT STARTED**

---

# Effective Next Boundary

The project is now beyond initial brainstorming and architecture design.

The next legitimate work is either:
1. deeper no-code benchmark analysis, or
2. only when explicitly authorized, a **minimal Phase 1 implementation plan**.

No implementation should start merely because the design documents are complete.

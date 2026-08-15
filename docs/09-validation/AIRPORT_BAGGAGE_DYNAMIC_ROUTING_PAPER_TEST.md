# Airport Baggage Dynamic Routing — 7-Artifact Paper Test

Status: **PASS ON PAPER with one additive field-level refinement**  
Episode class: `System Journey / Dynamic Discrete Routing`  
Implementation: **NONE**

Purpose: test whether the closed Civilization X-Ray harness works for a system where the hidden mechanism is not only geometry or continuous physical flow, but **identity + state + branching decisions + physical movement**.

This is a generic representative mechanism test, not a claim that all airports share one exact topology or algorithm.

---

# 1. P1 Episode Brief

## Candidate question
> **수하물 수천 개가 동시에 움직이는데, 내 가방은 어떻게 맞는 비행기로 가는가?**

## Viewer surface intuition
“컨베이어 벨트가 그냥 비행기 쪽으로 이어져 있을 것”이라는 overly-simple mental model.

## Hidden mechanism
The useful explanation is the coupling between:
- bag identity/tracking state;
- physical handling/sortation infrastructure;
- route/transfer/loading events;
- exception/recovery state.

## Explanatory unit
`one representative bag journey through a generic airport handling network`

## Scope lock
Included:
- acceptance/check-in state;
- tracking identity as a semantic anchor;
- generic handling/sortation nodes;
- branching route decisions as explanatory abstraction;
- load/transfer/arrival tracking points where supported by public standards;
- one exception/counterfactual path.

Excluded:
- airport-specific proprietary routing algorithms;
- exact conveyor counts/speeds/layouts;
- security screening internals not supported by public authoritative evidence;
- claim that barcode/RFID/device mix is identical everywhere;
- baggage rules unrelated to the routing mechanism.

## Case anchor
No single airport.

`case_anchor = GENERAL_MECHANISM / IATA_STANDARD_CONTEXT`

## Early truth label
All network topology shown is `SCHEMATIC REPRESENTATIVE`, unless a future real-airport case provides evidence for exact topology.

Topic Gate: **PASS**

Reason:
- high X-Ray value;
- hidden process;
- physical + information flow coupling;
- different harness stress than Venice/aqueduct/tunnel.

---

# 2. P2 Evidence Pack

## Evidence Claims

### BAG-C01 — baggage journey is an end-to-end lifecycle
Status: VERIFIED / authoritative current industry source.

IATA describes the baggage journey as the complete lifecycle from acceptance at origin to return to the passenger at final destination.

Visual implication:
- journey may be represented as staged custody/processing states, not one undifferentiated conveyor.

### BAG-C02 — Resolution 753 has four core tracking points
Status: VERIFIED.

Current IATA guidance identifies:
1. passenger handover / acceptance;
2. loading onto aircraft;
3. delivery to transfer area;
4. return/delivery to passenger at arrival.

Visual implication:
- these are strong evidence-backed lifecycle anchors;
- they do NOT define every internal conveyor/sort decision between them.

### BAG-C03 — airport infrastructure generates tracking data
Status: VERIFIED at category level.

IATA identifies airport infrastructure such as:
- Baggage Handling System (BHS)
- Baggage Reconciliation System (BRS)
- sortation systems
- arrival scanning facilities

as important sources of tracking data supporting Resolution 753.

Visual implication:
- physical movement and information state can legitimately be explained together.

### BAG-C04 — implementation varies
Status: VERIFIED as a general caution.

IATA notes differences in airport infrastructure maturity, technological readiness and capabilities.

Visual implication:
- no universal exact layout/technology claim;
- representative network must be explicitly schematic.

## Research unknowns intentionally NOT filled

- exact scanner technology at a given airport;
- exact route-decision algorithm;
- exact belt topology;
- exact timing thresholds;
- screening sequence beyond public evidence.

Research Gate: **PASS for paper-harness validation**

Condition for real episode:
A production episode would need additional primary/vendor/airport source evidence before presenting machinery topology as real.

---

# 3. P3 Story Pack

## Story structure
Selected grammar: `E3 System Journey` with Mystery hook.

### Beat B0 — Disappearance
A passenger hands over a bag; it disappears behind a wall.

Viewer question:
“How can this one object remain associated with the right journey after it leaves me?”

### Beat B1 — Identity before movement
Introduce one highlighted representative bag/token.

Core idea:
The viewer must be able to follow **the same bag** across all later views.

### Beat B2 — Open the hidden network
Terminal surface peels away / schematic network appears.

Do not show one magical direct belt.
Show categories of nodes and branches without pretending exact airport topology.

### Beat B3 — Physical route + information state
At each relevant explanatory node, the bag has:
- current identity reference;
- current route/destination intent;
- current custody/tracking state.

Narration does not claim a universal proprietary algorithm.

### Beat B4 — Branch decision
The bag reaches a branch where multiple physical paths are possible.

Visual proof objective:
A state/data condition selects one branch in the explanatory schematic.

### Beat B5 — Handoff / loading
Use the IATA tracking anchor around aircraft loading.

Key distinction:
`where the bag physically is` and `what the system knows about its journey` are related but not identical concepts.

### Beat B6 — Transfer stress test
Counterfactual:
What if destination/flight state changes because the bag must transfer?

Do not claim a specific airport algorithm.
Use it to demonstrate that a journey is a stateful route, not one fixed line.

### Beat B7 — Arrival
Use final tracked handoff/arrival anchor.

### Beat B8 — Reassembly / payoff
Return to the passenger-side airport view.

Payoff:
The hidden system is not merely belts. It is **physical routing tied to an identity/tracking journey**.

## Story Gate
PASS.

Reason:
- central mechanism remains one concept;
- data state is always attached to visible physical action;
- no IT architecture detour.

---

# 4. P4 Visual Plan

The narration may be longer than the visual work-order count.
One visual objective can support several narration units.

## V01 — BAG_HANDOFF
Medium: REAL_REFERENCE or controlled illustrative scene.

Purpose:
establish same-bag semantic identity.

Continuity:
SEMANTIC + TEMPORAL.

## V02 — SURFACE_TO_NETWORK
Medium: BLENDER / 2D HYBRID.

Action:
terminal/context → schematic hidden route network reveal.

Truth:
SCHEMATIC / representative.

## V03 — BAG_IDENTITY_LOCK
Medium: 2D overlay + schematic geometry.

Action:
highlight bag token and persistent identity marker.

Purpose:
viewer can always recognize same bag.

## V04 — JOURNEY_STATE_MAP
Medium: 2D.

Action:
show evidence-backed lifecycle anchors separately from illustrative internal nodes.

Purpose:
prevent false precision.

## V05 — BRANCH_DECISION
Medium: BLENDER or 2D deterministic.

Entry state:
Bag at node N with route state A.

Exit state:
Bag follows branch A; non-selected route visually de-emphasized.

Proof question:
Can the viewer see that one state decision has a physical consequence?

## V06 — MERGE_WITH_OTHER_BAGS
Medium: deterministic Blender/2D.

Purpose:
many bags share infrastructure but semantic identity of hero bag survives.

Continuity:
SEMANTIC + SPATIAL + TEMPORAL.

## V07 — LOAD_HANDOFF
Medium: simplified 2D/3D + real/reference context.

Claim anchor:
Resolution 753 loading tracking point.

## V08 — TRANSFER_COUNTERFACTUAL
Medium: 2D network first, then optional Blender.

Action:
state changes → old route becomes invalid → new branch highlighted.

Truth:
conceptual mechanism, not airport-specific algorithm.

## V09 — ARRIVAL_TRACKING
Medium: 2D/real context.

Claim anchor:
arrival/delivery tracking point.

## V10 — NETWORK_REASSEMBLY
Medium: BLENDER/2D pull-out.

Action:
single bag route → entire generic network → passenger-facing terminal.

Payoff:
physical infrastructure + state information as one system.

## Medium router verdict

Central explanation does **not** need generative video.

Preferred:
- 2D = state/data/routing explanation;
- Blender = deterministic network/spatial continuity when added value exists;
- real/reference media = airport context;
- generative video = optional atmosphere only.

Visual Gate: **PASS**

---

# 5. P5 Spatial / Asset Bible

## Hero scope
`SYSTEM`

## Canonical system representation
A deliberately simplified network graph embedded in a spatial airport/baggage context.

## Components
Generic semantic categories only:
- acceptance/handoff node
- handling path segment
- sort/divert decision node
- merge node
- load handoff node
- transfer handoff node
- arrival/delivery node

These are explanatory component categories, not a claim about exact architecture at every airport.

## Component relationships
Represent:
- route adjacency;
- branch/merge relationship;
- custody/tracking anchor relationship where evidence supports it.

## Hard locks
- hero bag identity never changes silently;
- selected route connects only through declared network edges;
- route does not teleport between nodes;
- same branch node has stable input/output relationships across shots;
- IATA evidence-backed tracking anchors are not conflated with every illustrative internal sort node;
- schematic network is labeled representative.

## Semantic anchor
`BAG-001` — one highlighted representative bag.

## Existing continuity classes test

### SEMANTIC
Same bag / same destination journey.

### TEMPORAL
State transitions happen in order.

### SPATIAL
Bag occupies a valid path/node.

### OBJECT
Physical bag appearance when it is visually identifiable.

Verdict:
**The existing four continuity classes are sufficient. No fifth `OPERATIONAL` class is necessary.**

## Gap discovered: shared behavioral invariants

Geometry fields alone are not enough to avoid duplicated route/state logic across shots.

Required small refinement:
P5 should optionally support a shared field such as:
- `behavioral_invariants[]`
- `state_schema[]` when the central mechanism is stateful
- `routing_or_transition_rule_refs[]` where needed

These fields describe explanatory system truth, not proprietary production code.

Examples for this paper test:
- a bag's semantic identity persists across state transitions;
- state changes must be visually attributable to a declared event/decision;
- a bag cannot occupy two mutually exclusive route states simultaneously unless explicitly explaining duplication/error;
- route visuals must follow the canonical network graph.

Spatial/Asset Gate: **PASS WITH ADDITIVE FIELD REFINEMENT**

---

# 6. P6 Production Pack

## Planned reusable production assets

### BAG-NETWORK-G1
- deterministic schematic network
- nodes/edges addressable by ID
- branch highlighting
- bag token animation
- optional simplified terminal spatial shell

### BAG-STATE-OVERLAY
- identity
- lifecycle state
- route target
- evidence vs illustrative node styling

### BAG-CONTEXT
- real/reference airport footage or licensed stills for context only

## Generation policy

No generative model may invent the canonical route topology used as explanatory evidence.

Generative video may only be used for:
- atmospheric passenger/airport context;
- non-authoritative transitions;
- optional cinematic establishing shots.

## Cost implication

This mechanism class is relatively cheap:
- central truth is 2D/deterministic procedural graphics;
- one network model is reusable across many shots;
- expensive video generation adds little explanatory value.

## Production Gate
PASS on paper.

---

# 7. P7 Review & Run Ledger — Fault Injection

Two deliberate changes test stale propagation.

## Fault A — route/destination state changes after Visual Lock

Initial:
`BAG-001 → route A → load state A`

Revision:
Story/evidence context now requires the transfer example to route BAG-001 through route B.

### Must become STALE/REVIEW
- V05 branch decision if its route state is affected;
- V08 transfer counterfactual;
- subsequent route overlays depending on B;
- related narration/TTS/captions;
- network animation keyframes referencing old branch.

### Should NOT automatically become stale
- generic network geometry if topology unchanged;
- airport establishing context;
- unrelated lifecycle explanation;
- P5 component identities not touched by route-state change.

Verdict:
field-aware stale propagation works.

## Fault B — representative network is mistakenly relabeled as one named airport's exact topology

Impact:
This is not a style change. It changes truth/reconstruction scope.

### Must block/revise
- Episode Brief case anchor/scope;
- Evidence Pack support;
- Spatial Bible truth label;
- all Visual shots presenting topology as factual;
- title/thumbnail if they imply exact airport internals;
- release qualifier.

Verdict:
existing representative-vs-universal safeguards correctly trigger upstream rollback.

---

# 8. QA Dry Run

## Factual
PASS for the limited paper claims.

IATA-backed lifecycle/tracking points are distinguished from illustrative routing internals.

## Script↔Visual
PASS.

Every data/state sentence causes or explains a visible physical route/state action.

## Spatial
PASS.

Graph/node/branch relation can be deterministically maintained.

## Semantic continuity
PASS.

BAG-001 is persistent.

## Temporal continuity
PASS.

State transitions are ordered.

## Reconstruction truth
PASS IF representative schematic label survives final edit.

## Cost/repeatability
PASS.

Central explanation can be produced primarily with reusable 2D/Blender assets.

---

# 9. Harness Findings

## Finding DR1 — Seven artifacts still sufficient
No new Dynamic System Manifest is needed.

## Finding DR2 — Spatial Bible is really a Spatial / System Bible
Its existing `system` hero scope is correct, but dynamic systems need optional stable behavioral/state invariants in addition to geometry.

## Finding DR3 — Four continuity classes remain sufficient
Operational state does not justify a fifth class.
Use:
- semantic identity;
- temporal state order;
- spatial route validity.

## Finding DR4 — 2D becomes even more important
Data/routing/state is clearer in 2D than forcing it into photorealistic 3D.

## Finding DR5 — Generative video is weak central evidence here
This further validates capability routing based on explanatory function rather than visual spectacle.

## Finding DR6 — state changes need field-aware invalidation
A route-state change should not invalidate network geometry when topology is unchanged.

---

# 10. Final Verdict

Dynamic discrete-routing mechanism class: **PASS ON PAPER**

7 core artifacts: **PASS**

Stage-Gated Artifact Blackboard: **PASS**

Thin Director: **PASS**

New top-level orchestra: **NO**

New core artifact: **NO**

New continuity class: **NO**

Contract refinement required: **YES, small P5 optional behavioral/state invariant fields**

Implementation required now: **NO**

## Closure impact

This fills the largest remaining mechanism-class gap in the no-code harness tests:
- static structure
- continuous flow
- construction geometry
- failure/stress
- **dynamic discrete routing/control**

No additional paper pilot is justified before new empirical evidence exposes a genuinely different contract failure.

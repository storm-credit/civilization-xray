# Mechanism-Class Gap Audit

Status: **No-code / post-Closure empirical audit**  
Purpose: determine whether any genuinely different mechanism class still deserves a paper test before implementation.  
Rule: do not create a new pilot merely to add documentation.

---

# 1. Already Tested Mechanism Classes

## A. Hidden static/spatial structure
Example: Venice foundations.

Tests:
- section/cutaway
- spatial hard locks
- representative-vs-universal reconstruction
- load path
- reassembly

Status: covered.

## B. Continuous physical flow / system journey
Example: Roman aqueduct.

Tests:
- source→route→destination
- gradient/flow direction
- semantic continuity across map/2D/3D
- system + components

Status: covered.

## C. Deterministic construction geometry / alignment
Example: undersea tunnel alignment.

Tests:
- coordinates/axes
- exact spatial relation
- schematic exaggeration
- 2D geometry before 3D

Status: covered.

## D. Failure / stress / sacrificial mechanism
Evidence strengthened by Practical Engineering transcript corpus.

Tests/concepts:
- counterfactual
- failure propagation
- safeguard activation
- tradeoff

Status: grammar-level coverage strong; full episode paper artifact run not necessary solely for this class.

---

# 2. Candidate Missing Classes — Four Alternatives

Scores: 1 low → 5 high.

| Candidate | What is genuinely new? | X-Ray value | Difference from existing pilots | Evidence availability | Harness stress value | Total |
|---|---|---:|---:|---:|---:|---:|
| A. Airport baggage routing | discrete items + scans + sort decisions + exception paths | 5 | 5 | 5 | 5 | **20** |
| B. Electric-grid frequency balancing | distributed control + invisible state + feedback | 5 | 5 | 4 | 5 | **19** |
| C. Metro/rail signalling | state authority + blocks + safety interlocks | 5 | 5 | 4 | 5 | **19** |
| D. Smart-building HVAC control | sensor feedback + zones + thermal flows | 4 | 4 | 4 | 4 | **16** |

## Why A is selected

Airport baggage handling is explicitly within the project's Movement Systems/System Journey scope, but unlike an aqueduct it is not one continuous material flow.

A bag's journey depends on:
- identity/tracking events;
- handoffs/custody state;
- route decisions;
- system components that may branch/merge;
- timing/connection constraints;
- exception/recovery paths.

Official IATA material confirms that baggage tracking is an end-to-end journey and identifies four mandatory tracking points under Resolution 753. IATA also identifies airport infrastructure including Baggage Handling Systems (BHS), Baggage Reconciliation Systems (BRS), sortation and arrival scanning as important sources of tracking data.

Therefore this is a good test of a missing **dynamic discrete-routing / state-machine mechanism class** without introducing speculative proprietary airport-specific details.

---

# 3. Scope Lock for the Paper Test

Working question:
> **수하물 수천 개가 동시에 움직이는데, 내 가방은 어떻게 맞는 비행기로 가는가?**

Scope:
- generic representative airport baggage journey;
- identity/tracking/routing as the central mechanism;
- check-in/acceptance → handling/sortation → aircraft loading as the explanatory spine;
- transfer/arrival used only where they clarify state and exception logic.

Not claimed:
- that every airport uses identical conveyor topology;
- a single universal scanner/RFID/barcode implementation;
- a specific airport's proprietary routing algorithm;
- security screening internals beyond public authoritative evidence;
- exact sortation speed/capacity without source.

Official evidence anchor for the paper test:
- IATA baggage journey / Resolution 753;
- IATA current tracking points and airport system roles.

---

# 4. Harness Questions to Test

The pilot is useful only if it answers these contract questions.

## Q1. Can Spatial / Asset Bible represent a network, not only an object?
Need:
- nodes
- edges/routes
- merge/divert relationship
- stable component identity

Existing `component_registry[]` + `component_relationships[]` may be sufficient.

## Q2. Where does stable behavioral logic live?
Examples:
- if bag identity/state says route A, divert A;
- after a handoff, custody/tracking state changes;
- exception state may reroute the item.

Current P5 locks geometry, but it does not explicitly name behavioral/state invariants.

Test whether this can live cleanly as:
- P5 shared `behavioral_invariants[]`, or
- P4 shot-local state only.

Hypothesis:
Shared system logic belongs in P5 because many shots must agree on it.

## Q3. Are four continuity classes enough?
Potential new concern: operational state continuity.

Do NOT create a fifth class unless necessary.
Try to model it as:
- SEMANTIC: same bag/identity/journey;
- TEMPORAL: correct before/after state;
- SPATIAL: correct route/node relation.

## Q4. Can one narration journey remain understandable across branch views?
Need stable semantic anchor:
- one highlighted bag/token;
- persistent destination/flight state;
- route trace.

## Q5. Does medium routing remain valid?
Expected:
- 2D for state/data/sort logic;
- Blender for spatial conveyor/network reveal where useful;
- real/reference context for airport exterior/process;
- generative video only for non-authoritative atmosphere if needed.

Exact routing must not be handed to a generative model as factual topology.

---

# 5. Pre-Mortem

If this paper test fails, likely causes:

1. **Spatial Bible is too geometry-centric**
   - symptom: route/state rules duplicated in every shot.
   - response: add a small behavioral-invariant field, not a new artifact.

2. **System Journey assumes one continuous route**
   - symptom: branches/exception paths make story incoherent.
   - response: make one bag the semantic anchor and treat branches as controlled counterfactuals.

3. **Generic mechanism overclaims airport uniformity**
   - symptom: viewer could think all airports share the same topology/technology.
   - response: representative/generic qualifier and source-bounded claims.

4. **Too much data-flow abstraction**
   - symptom: it becomes an IT architecture lecture rather than visible infrastructure.
   - response: every state/data explanation must cause a visible physical routing action.

5. **AI-generated conveyor topology drifts**
   - symptom: diverters/routes change between shots.
   - response: deterministic Blender/2D owns topology; generative video is optional context only.

---

# 6. Decision

Run **one compact full-artifact paper test** for Airport Baggage Dynamic Routing.

Success criteria:
- all 7 core artifact responsibilities can be represented;
- branching/state logic has one stable owner;
- no new continuity class is needed unless existing four fail;
- no eighth physical artifact is needed;
- routing remains explainable with Blender/2D without proprietary fake precision;
- any contract change is field-level and evidence-driven.

If these pass, no additional mechanism-class paper pilots are justified before implementation evidence.

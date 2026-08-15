# Dynamic System Contract Addendum v1

Status: **Additive field-level refinement after dynamic-routing paper test**  
Applies to: P5 Spatial / Asset Bible when the central mechanism includes operational state, routing, control or feedback.  
Does not create a new artifact or continuity class.

---

# 1. Why This Addendum Exists

The original P5 contract is strong for:
- object topology;
- component relationships;
- axes/orientation;
- spatial hard locks;
- reconstruction zones.

The Airport Baggage Dynamic Routing paper test exposed a different shared invariant:

> multiple shots may share not only the same geometry, but the same **allowed state transitions / route logic**.

If this logic lives only inside individual Visual Plan shots, agents may duplicate or contradict it.

Therefore P5 gains optional dynamic-system fields.

---

# 2. Optional P5 Fields for Stateful Systems

Use only when the episode mechanism requires them.

- `behavioral_invariants[]`
  - stable system behaviors that many shots must preserve
- `state_schema[]`
  - named explanatory states and their meanings
- `routing_or_transition_rule_refs[]`
  - references to evidence-backed or explicitly schematic transition/routing rules
- `stateful_component_ids[]`
  - components whose behavior depends on state
- `allowed_state_transitions[]`
  - when useful for deterministic explanatory animation
- `forbidden_state_combinations[]`
  - impossible/misleading combinations that QA should reject

These fields are semantic contract fields, **not executable production code**.

---

# 3. Truth Boundary

A behavioral invariant can have the same evidence classes as spatial geometry.

Examples:
- `VERIFIED_STANDARD` — supported by authoritative standard/source;
- `CASE_VERIFIED` — supported for a named real system;
- `REPRESENTATIVE_SCHEMATIC` — pedagogical abstraction of a class of systems;
- `COUNTERFACTUAL` — deliberately altered to demonstrate failure/alternative.

Rules:
- representative routing logic must not be displayed as one named facility's exact proprietary algorithm;
- AI/generative output must not invent unknown behavioral rules and promote them to verified truth;
- an exact state transition that is evidence-relevant must reference a claim/source or be labeled schematic.

---

# 4. Existing Continuity Classes Remain Locked

Do not add `OPERATIONAL_CONTINUITY` as a fifth default class.

Dynamic systems map cleanly to existing dimensions:

- `OBJECT` — same physical subject/component where relevant;
- `SPATIAL` — valid node/path/location;
- `SEMANTIC` — same identity, signal, packet, bag, vehicle or flow token;
- `TEMPORAL` — valid before/after state order.

A dynamic QA failure can cite multiple classes.

Example:
A highlighted bag jumps from route A to route B without a declared transition:
- SPATIAL fail — invalid path jump;
- SEMANTIC fail — same bag journey contradicted;
- TEMPORAL fail — missing state-transition event.

No new taxonomy is needed.

---

# 5. P4 Visual Plan Relationship

P5 owns shared invariant logic.
P4 owns shot-local state realization.

Use existing P4 fields:
- `entry_state`
- `exit_state`
- `camera_start_state`
- `camera_end_state`
- `hard_locks[]`
- `continuity_class[]`

For dynamic shots:
- entry/exit state should reference the relevant P5 state/rule IDs where practical;
- shot-local animation may simplify visualization but cannot violate P5 hard behavioral invariants.

---

# 6. Stale Propagation Rule

## Behavioral-rule change
If a P5 behavioral invariant/routing rule changes:

STALE/REVIEW only:
- Visual shots that reference that rule;
- dependent deterministic animation;
- narration explaining that transition;
- overlays/captions tied to it;
- downstream edit segments using the obsolete behavior.

Do NOT automatically invalidate:
- unrelated network geometry;
- unrelated components;
- atmosphere/context footage;
- claims not linked to the rule.

## Geometry-only change
Conversely, a visual geometry/style change that does not alter behavioral meaning does not automatically invalidate the state logic.

---

# 7. Applicability Beyond Baggage

These optional fields may support future topics such as:
- railway signalling/block states;
- elevator dispatch;
- port/container routing;
- power-grid switching/feedback explanations;
- floodgate operating states;
- building-control systems;
- traffic-control networks.

They are activated by mechanism need, not by content pillar.

---

# 8. Final Contract Verdict

- P5 physical artifact remains `Spatial / Asset Bible`.
- `hero_scope = system` remains sufficient.
- behavioral/state fields are optional extensions.
- P4 remains shot-local realization.
- four continuity classes remain sufficient.
- no new agent, orchestra, database or runtime framework is implied.

# 2026-08-15 — Dynamic Discrete-Routing Mechanism Validation

## Decision

- Previous decision / assumption: Venice, aqueduct and tunnel paper tests covered static spatial systems, continuous flow and construction/alignment, but the harness had not been explicitly exercised on discrete identity/state/routing systems even though Movement Systems/System Journey includes baggage.
- New decision: Run one final mechanism-class paper test using a generic airport baggage journey anchored to current IATA baggage/tracking standards. Keep the seven-artifact architecture and four continuity classes; add optional P5 behavioral/state invariant fields for stateful systems.
- Trigger / evidence: Mechanism-class 4-way gap audit ranked airport baggage routing highest for novelty and harness stress. The paper run showed that shared route/state logic should have one stable artifact owner, while operational continuity can already be expressed as SEMANTIC + TEMPORAL + SPATIAL continuity.
- Why changed: Without shared behavioral invariants, dynamic route logic could be duplicated inconsistently across shots. Creating a new artifact or fifth continuity class would be unnecessary overhead.
- Impact: P5 Spatial / Asset Bible gains optional dynamic-system semantics through `DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`. P4 entry/exit state continues to realize the logic per shot. Field-aware stale propagation is extended to behavior-rule changes.
- Reversible?: Yes; optional fields can be simplified if implementation evidence shows no value.
- Rollback path: remove the addendum and keep behavior fully shot-local only if prototype evidence proves shared state rules create more overhead than consistency.
- Affected files/stages: `MECHANISM_CLASS_GAP_AUDIT.md`, `AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md`, `DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`, `EMPIRICAL_VALIDATION_STATUS.md`.
- Follow-up validation: during Phase 1, test one deterministic state/routing animation and a route-state change to verify selective stale invalidation.

## Final verdict

- new orchestra: NO
- new artifact: NO
- fifth continuity class: NO
- P5 optional behavioral/state fields: YES
- additional no-code mechanism pilot required by current evidence: NO
- implementation: NOT STARTED

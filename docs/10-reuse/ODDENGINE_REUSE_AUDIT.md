# OddEngine → Civilization X-Ray Reuse Audit

Status: **Selective design reuse only — do not import the OddEngine pipeline wholesale**

Source repository: `storm-credit/oddengine` (`main` inspected 2026-08-14)

## Executive Decision

OddEngine contains useful production-orchestration ideas, but Civilization X-Ray already has a stronger domain architecture for evidence, spatial truth, long-form visual explanation and independent QA.

Therefore the rule is:

> Reuse only the concrete operational contracts that close current implementation gaps. Do not inherit OddEngine's MV-specific ontology, 16-stage pipeline, character-centric continuity, model-routing matrix, fixed shot counts, or UI structure.

Only three ideas are adopted now:

1. **Executable artifact gates**: a stage is not complete merely because state says `done`; required artifacts must actually exist, be readable, match schema/version expectations and not be stale.
2. **Explicit shot continuity bridge**: important generated-video shots record previous ending state, intended ending state, next start target, compatibility and risk.
3. **Durable prompt/reference provenance**: generation prompts and reference bindings must be persisted or immutably addressable; they cannot exist only in ephemeral agent/chat context.

Everything else is either already covered or intentionally deferred.

---

# 1. High-Value Findings

## 1.1 Video Orchestrator / Continuity Bible

Useful source patterns:
- one canonical continuity definition
- shot specs derive from that canonical definition
- explicit world/time/light/space/camera/reference constraints
- each shot has a start and ending state
- specialist handoff receives only the locked continuity block plus assigned shots
- repair/fallback is preferred over regenerating an entire sequence
- use the smallest useful model/tool set instead of invoking every generator

Civilization treatment:
- **keep the principle, not the MV schema**
- map character/world locks to the existing `Spatial / Asset Bible`, `Visual Plan`, `Shot Spec` and reconstruction metadata
- retain 180-degree/screen-direction thinking only where it materially helps viewer orientation
- do not add a second Continuity Bible artifact if the same truth already exists in the Spatial / Asset Bible and Shot Spec Pack

Decision: **ADAPT, no new duplicate artifact type.**

---

## 1.2 Veo Prompt Director

Useful source patterns:
- one primary visual event per generated shot
- explicit first-frame and last-frame states
- continuation uses previous ending state as the next bridge input
- references have a declared role and preservation boundary
- subject/action/environment/camera are separated from negative constraints
- failed hero shots should simplify or change a causal input rather than repeat blindly

Civilization treatment:
- add an explicit `Continuity Bridge` and `Reference Binding` record to the Veo Specialist contract
- keep deterministic spatial proof under Blender, not Veo
- do not adopt fixed 8-second assumptions or character/wardrobe-centric defaults

Decision: **HIGH-VALUE CONTRACT REUSE.**

---

## 1.3 `validate_manifest.py`

Useful source patterns:
- required-field validation
- enum/schema-like validation
- referenced-document existence checks
- strict vs warning modes
- machine-readable failure categories plus human-readable reporting

Important limit:
- OddEngine's completeness percentage measures field population, not creative or factual quality.

Civilization treatment:
- reuse the validation pattern for artifact contracts
- **do not use a field-completeness percentage as a quality score**
- quality remains the responsibility of explicit gate rubrics and independent reviewers

Decision: **REUSE VALIDATOR PATTERN, NOT QUALITY SEMANTICS.**

---

## 1.4 `track_gates.py`

This is the most important operational lesson in OddEngine.

The file distinguishes state-machine progress from physical asset verification. It checks whether expected files actually exist and, for some stages, whether they have plausible counts, parse correctly or exceed minimum size thresholds.

Civilization treatment:

A gate must be able to verify both:

### Logical state
- required upstream artifact IDs exist
- expected versions are current
- required reviewer verdict is PASS
- required human approval exists when applicable

### Material integrity
- referenced payload exists
- payload can be opened/parsed
- expected media type is valid
- required outputs are non-empty
- artifact hash/version matches registry metadata
- no hard dependency has made the artifact stale

Examples:
- `PREVIS PASS` cannot be satisfied by a status flag if the referenced storyboard/animatic is missing.
- `Generation Manifest` cannot be accepted if the generated media path is absent.
- `FINAL_REVIEW` cannot pass if required Fact / Continuity / Rights verdict artifacts are missing.

Decision: **ADOPT AS PHASE-1 EXECUTABLE GATE REQUIREMENT.**

---

## 1.5 `harness.py` / `advance_stage.py`

Useful source patterns:
- canonical stage order
- transition validation
- required gate before entering expensive downstream work
- stage owner metadata
- explicit backward/skip handling

Civilization already has a richer state machine and rollback model, so the OddEngine stage list should not be copied.

One adaptation is important:

> Any future `force` / override transition must write actor, reason, affected artifact versions and risk to the Episode Run Ledger.

A generic silent `--force` is not acceptable for evidence-sensitive production.

Decision: **PATTERN ONLY.**

---

## 1.6 Pipeline Status Dashboard

Useful source patterns:
- current stage
- owner
- subsystem state
- next actions
- stage matrix

Civilization already requires observability, but Phase 0/early Phase 1 does not need a dedicated dashboard implementation yet.

Decision: **DEFER.** Later CLI/UI may expose the same information from the Artifact Blackboard and Run Ledger.

---

# 2. Explicit Non-Reuse

Do not import these OddEngine choices into Civilization X-Ray:

- K-ghost/MV character anchor rules
- song/lyrics/Suno stages
- KR/US/ES track ontology
- fixed 16-stage music-video pipeline
- fixed 22-shot or other track-specific count assumptions
- `T1/T2/T3` MV animation tiers as global production truth
- exact model-routing claims such as one named generator always being the first choice
- model/version/cost assumptions without fresh verification
- generating prompts for all engines by default
- Remotion-specific file layout as the project ontology
- one YAML episode/track manifest as a second competing source of truth beside the Artifact Blackboard
- completeness percentage as a quality gate
- generic force-skip without recorded governance

---

# 3. Adopted Design Delta

## 3.1 Executable Gate Contract

Phase 1 gate evaluation should conceptually accept:

```text
GateRequest
- episode_id
- target_state
- required_artifact_ids
- required_versions
- required_verdicts
- required_human_approvals
```

and return:

```text
GateResult
- gate_id
- passed
- blocking_failures[]
- warnings[]
- missing_artifacts[]
- stale_artifacts[]
- invalid_payloads[]
- verdict_refs[]
- evaluated_at
```

State transitions consume `GateResult`; they do not infer completion from a string status alone.

## 3.2 Continuity Bridge Contract

For continuity-sensitive generated shots:

```text
ContinuityBridge
- previous_end_state
- intended_start_state
- intended_end_state
- next_start_target
- compatibility_note
- continuity_risk
```

This is especially useful for Veo/hybrid sequences and does not replace Spatial / Asset Bible locks.

## 3.3 Reference Binding Contract

Each important generation reference should declare:

```text
ReferenceBinding
- asset_id
- bound_role
- must_preserve[]
- may_reinterpret[]
- must_not_affect[]
```

Examples of `bound_role` in Civilization X-Ray:
- structure identity
- material appearance
- historical costume
- environment
- style only
- first-frame geometry anchor

This prevents a style reference from accidentally becoming false structural evidence.

## 3.4 Durable Prompt Provenance

Before a generated asset can be accepted, the Generation Manifest must contain either:
- the complete prompt payload, or
- an immutable prompt artifact ID + version/hash.

The same rule applies to reference bindings and first/last-frame assets.

Prompt text must not be recoverable only from chat history.

---

# 4. What This Changes — and What It Does Not

Changes:
- Phase 1 gate implementation must validate actual artifacts/payload integrity.
- Veo Specialist contract gains explicit bridge/reference-binding records.
- Generation provenance must persist prompt/reference versions.

Does not change:
- selected Stage-Gated Artifact Blackboard architecture
- four responsibility orchestras
- independent Visual/Fact/Rights QA
- Blender-first deterministic spatial explanation
- 2D as first-class explanatory capability
- AskAnything provider-reuse decision
- current design-first / no implementation-code phase

---

# 5. Reuse Matrix

| OddEngine asset/pattern | Reuse | Civilization treatment |
|---|---|---|
| `video-orchestrator/SKILL.md` | MEDIUM | Keep canonical continuity + minimal routing principles |
| `continuity-templates.md` | MED-HIGH | Adapt start/end state, space/light/camera locks; avoid duplicate Bible |
| `veo-prompt-director/SKILL.md` | HIGH | Adopt continuity bridge + reference binding + single-primary-event discipline |
| `validate_manifest.py` | HIGH pattern | Build artifact/schema validator; reject completeness-as-quality |
| `web/track_gates.py` | HIGH | Adopt logical + material gate verification |
| `web/harness.py` | MEDIUM | Reuse transition/gate enforcement concepts only |
| `advance_stage.py` | LOW-MED | Override concept only with mandatory ledgered reason/actor |
| `pipeline_status.py` | LOW now | Defer observability UI/CLI until runtime exists |
| `VISUAL_ANIMATION_ORCHESTRA_REPORT.md` | LOW | MV tiers/assets are domain-specific; current visual router is stronger |
| OddEngine track manifest ontology | LOW | Do not create competing source of truth |

---

# 6. Final Decision

OddEngine does **not** justify adding more orchestras, more specialist agents or a second manifest system.

Its useful contribution is narrower and operational:

> **make gates executable against real artifacts, make shot-to-shot continuity explicit, and make generation inputs reproducible.**

That is the complete reuse boundary for now.

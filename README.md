# Civilization X-Ray

> 인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 X-Ray/단면/흐름/재구성 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부하는 프로젝트.

## Current Status

**Architecture / contract design: CLOSED**  
**Harness: Stage-Gated Artifact Blackboard + Thin Director**  
**7 core physical artifacts: locked for Phase 1 planning**  
**Venice end-to-end paper run: PASS ON PAPER**  
**Dynamic discrete-routing baggage paper test: PASS ON PAPER**  
**10-video transcript/text benchmark: PASS / 10 OF 10**  
**10-video direct frame/timeline benchmark: PARTIAL / unobserved gaps remain**  
**Tool/provider capability snapshot: validated 2026-08-15, volatile**  
**YouTube AI disclosure/rights snapshot: validated 2026-08-15, volatile**  
**Implementation: NOT STARTED / NOT AUTHORIZED**

Architecture/contract design is now **closed and frozen**. Remaining uncertainty is empirical/runtime evidence, not another missing design layer.

Key closure results:
1. 7 physical core artifacts have field-level contracts.
2. Camera/Transition Grammar v1 is locked for Phase 1 planning.
3. Audio/Post Timeline Contract v1 is locked for Phase 1 planning.
4. `VX-PILOT-001 Venice Foundations` ran end-to-end through all four orchestras on paper.
5. factual-scope and wording-only fault injections validated field-aware stale propagation on paper.
6. 32 narration units compressed to 15 visual work orders rather than one generated clip per sentence.
7. one reusable Blender explanatory module + 2D can carry the Venice pilot’s central mechanism.
8. generative video remains optional cinematic context, not factual-geometry authority.
9. dynamic discrete routing/stateful systems were additionally tested with a generic airport baggage journey; no new orchestra, artifact or continuity class was required.
10. no fifth creative orchestra, eighth default core artifact, full-time modeler or implementation framework lock is justified before prototype evidence.

## Core Direction

채널 범위:
- Architecture
- Hidden Cities
- Historical Engineering
- Movement Systems
- Mega Infrastructure
- Failure X-Ray

공통 질문:

> **“이 영상에서 X-Ray로 보여줄, 눈에 보이지 않는 원리는 무엇인가?”**

이를 답할 수 없는 소재는 다루지 않는다.

## Selected Harness

> **Stage-Gated Artifact Blackboard + Thin Director**

하네스는 에이전트 숫자로 정의하지 않는다. responsibility / artifact / state / provenance / gate / retry / rollback / stale / memory / budget을 먼저 정의하고, 실제 physical agent 수와 구현 기술은 구현 직전에 최소한으로 결정한다.

### Seven core physical artifacts
1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Logical concepts such as Claim Ledger, Narration Script, Shot Spec, Generation Manifest and QA Report may live as sections/child records inside these seven artifacts.

## Studio Architecture

```text
Project Orchestrator
│
├─ Editorial & Research Orchestra
├─ Visual Production Orchestra
├─ Audio & Post Orchestra
└─ Release & Learning Orchestra

Cross-cutting:
├─ Fact / Rights / Quality Governance
└─ Shared Asset / Memory / Provider Health services
```

Visual production baseline:
- Blender: deterministic spatial truth / registered camera / cutaway / explode / reassembly
- 2D: maps / diagrams / elevation / causal flow / state/routing explanation
- Google/generative video capability: people / atmosphere / historical reconstruction / cinematic bridge where exact topology is not evidence
- Human modeler: escalation path only
- Higgsfield: not a required dependency

Provider/model names are implementation-time capability-registry data, not project constitution.

## Current Truth / Handoff

Start here:
- [`CLAUDE.md`](CLAUDE.md)
- [`docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md`](docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md)
- [`docs/00-project/CLAUDE_HANDOFF.md`](docs/00-project/CLAUDE_HANDOFF.md)
- [`docs/00-project/FINAL_DESIGN_BLUEPRINT.md`](docs/00-project/FINAL_DESIGN_BLUEPRINT.md)
- [`docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md`](docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md)

### Locked / additive contracts
- [`docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`](docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md)
- [`docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`](docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md)
- [`docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`](docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md)
- [`docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md`](docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md)
- [`docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md`](docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md)
- [`docs/11-design-closure/pilot-venice/`](docs/11-design-closure/pilot-venice/)

### Empirical validation
- [`docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md`](docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md)
- [`docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md`](docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md)
- [`docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md`](docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md)
- [`docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md`](docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md)
- [`docs/09-validation/MECHANISM_CLASS_GAP_AUDIT.md`](docs/09-validation/MECHANISM_CLASS_GAP_AUDIT.md)
- [`docs/09-validation/AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md`](docs/09-validation/AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md)

### Foundation / detailed systems
- [`docs/03-content/CONTENT_SYSTEM.md`](docs/03-content/CONTENT_SYSTEM.md)
- [`docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`](docs/04-script/SCRIPT_VISUAL_GRAMMAR.md)
- [`docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`](docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md)
- [`docs/06-production/AUDIO_POST_SYSTEM.md`](docs/06-production/AUDIO_POST_SYSTEM.md)
- [`docs/07-quality/QUALITY_SCORECARD.md`](docs/07-quality/QUALITY_SCORECARD.md)
- [`docs/02-harness/HARNESS_ARCHITECTURE.md`](docs/02-harness/HARNESS_ARCHITECTURE.md)
- [`docs/02-harness/STUDIO_ORCHESTRATION_V2.md`](docs/02-harness/STUDIO_ORCHESTRATION_V2.md)

### Reuse audits
- [`docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md`](docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md)
- [`docs/10-reuse/ODDENGINE_REUSE_AUDIT.md`](docs/10-reuse/ODDENGINE_REUSE_AUDIT.md)

### Decisions
- [`docs/99-decisions/CHANGE_LOG.md`](docs/99-decisions/CHANGE_LOG.md)

## Design Principles

- Design before implementation
- Context dump before prompting
- Ask only for truly missing context; do not repeat answered questions
- Four genuinely different alternatives for consequential decisions
- Blind-spot sweep and pre-mortem before consequential locks
- Evidence before completion claims
- Script ↔ Visual alignment over decorative AI footage
- Geometry when topology is explanatory evidence
- 2D diagrams when they explain better than 3D
- Blender-first deterministic camera when spatial motion teaches the explanation
- Human modeler is an escalation path, not a baseline dependency
- Cheap reasoning first, expensive pixels last
- Source → claim → script → visual/audio/package provenance
- field-aware stale propagation instead of whole-episode regeneration
- representative technique must not silently become universal truth
- narration unit count must not become generation count
- no silent fallback
- retry requires causal input change
- rights / AI disclosure / authenticity are Release Gate concerns
- record where/why plans changed and their impact

## References

Methodological references:
- `multica-ai/andrej-karpathy-skills`
- `bradautomates/claude-video`
- `obra/superpowers`
- `Egonex-AI/Understand-Anything` (former Lum1104 lineage)
- `rohitg00/agentmemory`

These are workflow/reasoning references, not code to copy wholesale.

## Next Boundary

Without implementation authorization, further work is justified only by new direct evidence, for example:
- direct frame/timeline benchmark evidence that is actually observable
- materially changed source/rights/platform policy
- materially changed provider capability
- a demonstrated mechanism/contract gap not already represented by current static/flow/alignment/failure/dynamic-routing coverage

Do **not** create more agents, orchestras, artifacts, framework choices or paper pilots merely to continue design activity.

When implementation is explicitly authorized, the next sequence is:

> **Implementation Readiness Review → runtime pre-mortem → 4 minimal implementation scopes → tool auditions/technology choices → Minimal Supervised Prototype plan → code**

## Implementation Lock

Do not add application code, automation code, API clients, agent-framework scaffolding, Blender runtime scripts, deployment configuration, publishing automation, or vendor-specific production integrations until implementation is explicitly authorized.

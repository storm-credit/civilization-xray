# Civilization X-Ray

> 인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 3D/X-Ray 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부하는 프로젝트.

## Current Status

**Phase 0 — Architecture Design: complete**  
**Validation 0.5 — Harness/artifact validation: complete**  
**Design Closure 0.6 — end-to-end contract validation: complete**  
**10-video frame-level benchmark corpus: partial / pending direct media access**  
**Implementation: not started / intentionally blocked until explicit authorization**

Closure 0.6 completed:
1. 7 physical core artifacts now have field-level contracts
2. camera/transition grammar locked for Phase 1 planning
3. Audio/Post timeline contract locked
4. `VX-PILOT-001 Venice Foundations` ran end-to-end through all four orchestras on paper
5. factual-scope and wording-only change fault injections validated field-aware stale propagation
6. 32 narration units compressed to 15 visual work orders rather than one video per sentence
7. one reusable Blender explanatory module + 2D can carry the pilot’s central mechanism
8. Veo remains optional cinematic context, not a factual-geometry dependency
9. no fifth creative orchestra, eighth default core artifact, or full-time modeler is justified before prototype evidence

Architecture/contract design is now **closed**. Remaining uncertainty is empirical, not another missing design layer.

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

**Stage-Gated Artifact Blackboard + Thin Director**

하네스는 에이전트 숫자로 정의하지 않는다. responsibility / artifact / state / provenance / gate / retry / rollback / memory / budget을 먼저 정의하고, 실제 physical agent 수와 기술은 구현 단계에서 최소한으로 결정한다.

### Phase 1 default core artifacts — field-tested in Closure 0.6
1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Logical concepts may remain more granular internally; physical files/artifacts are split only when actual complexity requires it.

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
└─ Shared Asset & Memory Service
```

Visual production baseline:
- Blender: deterministic spatial truth / registered camera / cutaway / explode / reassembly
- 2D: maps / diagrams / elevation / causal explanation
- Veo/Google video: cinematic reconstruction / people / atmosphere / bridge shots
- Human modeler: escalation path only
- Higgsfield: not a required dependency

## Design Entry Points

### Current truth / handoff
- [`CLAUDE.md`](CLAUDE.md)
- [`docs/00-project/CLAUDE_HANDOFF.md`](docs/00-project/CLAUDE_HANDOFF.md)
- [`docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md`](docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md)

### Closure 0.6 contracts
- [`docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`](docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md)
- [`docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md`](docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md)
- [`docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md`](docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md)
- [`docs/11-design-closure/pilot-venice/`](docs/11-design-closure/pilot-venice/)

### Foundation design
- [`docs/00-project/FINAL_DESIGN_BLUEPRINT.md`](docs/00-project/FINAL_DESIGN_BLUEPRINT.md)
- [`docs/00-project/PROJECT_CHARTER.md`](docs/00-project/PROJECT_CHARTER.md)
- [`docs/09-validation/VALIDATION_0_5_FINAL.md`](docs/09-validation/VALIDATION_0_5_FINAL.md)

### Discovery / Risks
- [`docs/01-discovery/PHASE0_DECISIONS.md`](docs/01-discovery/PHASE0_DECISIONS.md)
- [`docs/01-discovery/REFERENCE_REVERSE_ENGINEERING.md`](docs/01-discovery/REFERENCE_REVERSE_ENGINEERING.md)
- [`docs/01-discovery/BLIND_SPOT_SWEEP.md`](docs/01-discovery/BLIND_SPOT_SWEEP.md)
- [`docs/01-discovery/FULL_STUDIO_BLIND_SPOT_SWEEP.md`](docs/01-discovery/FULL_STUDIO_BLIND_SPOT_SWEEP.md)
- [`docs/01-discovery/RISK_REGISTER.md`](docs/01-discovery/RISK_REGISTER.md)

### Harness
- [`docs/02-harness/HARNESS_DESIGN_POLICY.md`](docs/02-harness/HARNESS_DESIGN_POLICY.md)
- [`docs/02-harness/HARNESS_ARCHITECTURE.md`](docs/02-harness/HARNESS_ARCHITECTURE.md)
- [`docs/02-harness/STUDIO_ORCHESTRATION_V2.md`](docs/02-harness/STUDIO_ORCHESTRATION_V2.md)

### Content / Script / Visual / Audio
- [`docs/03-content/CONTENT_SYSTEM.md`](docs/03-content/CONTENT_SYSTEM.md)
- [`docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`](docs/04-script/SCRIPT_VISUAL_GRAMMAR.md)
- [`docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`](docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md)
- [`docs/06-production/AUDIO_POST_SYSTEM.md`](docs/06-production/AUDIO_POST_SYSTEM.md)

### Reuse audits
- [`docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md`](docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md)
- [`docs/10-reuse/ODDENGINE_REUSE_AUDIT.md`](docs/10-reuse/ODDENGINE_REUSE_AUDIT.md)

### Decisions
- [`docs/99-decisions/CHANGE_LOG.md`](docs/99-decisions/CHANGE_LOG.md)

## Design Principles

- Design before implementation
- Context dump before prompting
- Ask only for truly missing context; do not repeat answered questions
- Four alternatives for consequential design decisions
- Blind-spot sweep and pre-mortem before architecture/implementation lock
- Evidence before completion claims
- Script ↔ Visual alignment over decorative AI footage
- Geometry when topology is explanatory evidence
- 2D diagrams when they explain better than 3D
- Blender-first deterministic camera when spatial motion teaches the explanation
- Human modeler is an escalation path, not a baseline dependency
- Cheap reasoning first, expensive pixels last
- Source → claim → script → visual provenance
- field-aware stale propagation instead of whole-episode regeneration
- representative technique must not silently become universal truth
- narration unit count must not become generation count
- record where/why plans changed and their impact

## References

Methodological references currently studied:
- `multica-ai/andrej-karpathy-skills`
- `bradautomates/claude-video`
- `obra/superpowers`
- `Egonex-AI/Understand-Anything` (originally Lum1104)
- `rohitg00/agentmemory`

These are references for workflow and reasoning patterns, not code to copy wholesale.

## Next Boundary

Without implementation authorization, allowed work is limited to empirical no-code refinement such as:
- direct benchmark transcript+frame analysis
- source/rights research
- current official provider capability validation
- a genuinely new mechanism-class paper test only if it exposes a contract failure

When the user explicitly authorizes implementation, the next step is:

> **Phase 1 Minimal Supervised Prototype implementation plan**

Do not start with a full autonomous agent platform, UI, vector DB, deployment stack, or every specialist as a separate physical process.

## Implementation Lock

Do not add application code, automation code, API clients, agent-framework scaffolding, deployment configuration, or vendor-specific production integrations until implementation is explicitly authorized.

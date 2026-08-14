# Civilization X-Ray

> 인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 3D/X-Ray 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부하는 프로젝트.

## Current Status

**Phase 0 — Design: complete**  
**Validation 0.5 — Paper/harness validation: complete; frame-level reference corpus remains pending direct media access**  
**Implementation: not started / intentionally blocked**

No-code validation completed:
1. 3 representative episode paper walkthroughs
2. artifact/harness overengineering review
3. 12 logical artifacts → 7 default physical core artifacts for Phase 1
4. Hero Object model → Spatial / Asset Bible (`object | system | component`)
5. continuity expanded to object / spatial / semantic / temporal
6. scale treatment metadata added
7. 2D diagram/motion graphics promoted to first-class explanatory capabilities
8. Blender-first model acquisition + deterministic camera/render router designed
9. validation-driven changes recorded in `CHANGE_LOG.md`

Still pending before/alongside implementation planning when media access is available:
- actual 10-video timestamp transcript + frame reverse-engineering corpus

This remaining empirical work may refine script/camera grammar, but does not change the selected harness topology unless evidence contradicts the current design.

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

하네스는 에이전트 숫자로 정의하지 않는다.

먼저:
- responsibility
- artifact
- state
- provenance
- gate
- retry / rollback
- memory
- budget

를 정의하고, 실제 agent 수와 기술은 구현 단계에서 최소한으로 결정한다.

### Phase 1 default core artifacts
1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Logical concepts may remain more granular internally; physical files/artifacts are split only when complexity requires it.

## Design Entry Points

### Project Rules
- [`CLAUDE.md`](CLAUDE.md)
- [`docs/00-project/PROJECT_CHARTER.md`](docs/00-project/PROJECT_CHARTER.md)
- [`docs/00-project/FINAL_DESIGN_BLUEPRINT.md`](docs/00-project/FINAL_DESIGN_BLUEPRINT.md)

### Discovery / Risks
- [`docs/01-discovery/PHASE0_DECISIONS.md`](docs/01-discovery/PHASE0_DECISIONS.md)
- [`docs/01-discovery/REFERENCE_REVERSE_ENGINEERING.md`](docs/01-discovery/REFERENCE_REVERSE_ENGINEERING.md)
- [`docs/01-discovery/BLIND_SPOT_SWEEP.md`](docs/01-discovery/BLIND_SPOT_SWEEP.md)
- [`docs/01-discovery/RISK_REGISTER.md`](docs/01-discovery/RISK_REGISTER.md)

### Harness
- [`docs/02-harness/HARNESS_DESIGN_POLICY.md`](docs/02-harness/HARNESS_DESIGN_POLICY.md)
- [`docs/02-harness/HARNESS_READINESS_REVIEW.md`](docs/02-harness/HARNESS_READINESS_REVIEW.md)
- [`docs/02-harness/HARNESS_ARCHITECTURE.md`](docs/02-harness/HARNESS_ARCHITECTURE.md)

### Content / Script / Visual
- [`docs/03-content/CONTENT_SYSTEM.md`](docs/03-content/CONTENT_SYSTEM.md)
- [`docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`](docs/04-script/SCRIPT_VISUAL_GRAMMAR.md)
- [`docs/05-visual/VISUAL_SYSTEM.md`](docs/05-visual/VISUAL_SYSTEM.md)
- [`docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`](docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md)

### Production / Quality / Prompts
- [`docs/06-production/PRODUCTION_SYSTEM.md`](docs/06-production/PRODUCTION_SYSTEM.md)
- [`docs/07-quality/QUALITY_SCORECARD.md`](docs/07-quality/QUALITY_SCORECARD.md)
- [`docs/08-prompts/META_PROMPT_SYSTEM.md`](docs/08-prompts/META_PROMPT_SYSTEM.md)

### Validation 0.5
- [`docs/09-validation/PAPER_WALKTHROUGHS.md`](docs/09-validation/PAPER_WALKTHROUGHS.md)
- [`docs/09-validation/ARTIFACT_PRUNING_REVIEW.md`](docs/09-validation/ARTIFACT_PRUNING_REVIEW.md)
- [`docs/09-validation/REFERENCE_DESK_VALIDATION.md`](docs/09-validation/REFERENCE_DESK_VALIDATION.md)
- [`docs/09-validation/VALIDATION_0_5_FINAL.md`](docs/09-validation/VALIDATION_0_5_FINAL.md)

### Decisions
- [`docs/99-decisions/CHANGE_LOG.md`](docs/99-decisions/CHANGE_LOG.md)

## Design Principles

- Design before implementation
- Context dump before prompting
- Ask for missing context or record reversible assumptions
- Four alternatives for consequential design decisions
- Blind-spot sweep and pre-mortem before architecture lock
- Evidence before completion claims
- Script ↔ Visual alignment over decorative AI footage
- Geometry when topology is explanatory evidence
- 2D diagrams when they explain better than 3D
- Blender-first deterministic camera when spatial motion teaches the explanation
- Human modeler is an escalation path, not a baseline dependency
- Cheap reasoning first, expensive pixels last
- Source → claim → script → visual provenance
- Record where/why plans changed and their impact

## References

Methodological references currently studied:
- `multica-ai/andrej-karpathy-skills`
- `bradautomates/claude-video`
- `obra/superpowers`
- `Egonex-AI/Understand-Anything` (originally Lum1104)
- `rohitg00/agentmemory`

These are references for workflow and reasoning patterns, not code to copy wholesale.

## Implementation Lock

Do not add application code, automation code, API clients, agent-framework scaffolding, deployment configuration, or vendor-specific production integrations until implementation is explicitly authorized.

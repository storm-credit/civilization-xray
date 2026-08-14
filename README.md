# Civilization X-Ray

> 인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 3D/X-Ray 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부하는 프로젝트.

## Current Status

**Phase 0 — Design: architecture-level complete**  
**Implementation: not started / intentionally blocked**

다음 단계는 코딩이 아니라 **Validation 0.5**다.

1. 실제 레퍼런스 롱폼 10편을 transcript + frames로 역설계
2. 서로 다른 episode grammar 3개를 paper walkthrough
3. artifact/harness 과설계 여부 재검토
4. 변경점은 `docs/99-decisions/CHANGE_LOG.md`에 기록
5. 검증 후에만 Phase 1 최소 구현 설계로 이동

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

### Production / Quality / Prompts
- [`docs/06-production/PRODUCTION_SYSTEM.md`](docs/06-production/PRODUCTION_SYSTEM.md)
- [`docs/07-quality/QUALITY_SCORECARD.md`](docs/07-quality/QUALITY_SCORECARD.md)
- [`docs/08-prompts/META_PROMPT_SYSTEM.md`](docs/08-prompts/META_PROMPT_SYSTEM.md)

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

Do not add application code, automation code, API clients, agent-framework scaffolding, deployment configuration, or vendor-specific production integrations until the design validation gates have passed and implementation is explicitly authorized.

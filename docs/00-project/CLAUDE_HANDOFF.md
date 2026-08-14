# Civilization X-Ray — Claude Continuation Handoff

Status: **Paste-ready / repository-first continuation guide**

This document exists so a new Claude / Claude Code session can continue without reconstructing prior chat history.

## 1. Repository

- Repository: `storm-credit/civilization-xray`
- Default branch: `main`
- Project type: long-form documentary/explainer production system
- Current implementation state: **NOT STARTED**
- Current design state: **Phase 0 architecture + Validation 0.5 design validation complete**
- Remaining empirical benchmark state: **frame-level 10-video benchmark analysis PARTIAL**

## 2. First Read Order

Before making decisions, read these files in order:

1. `CLAUDE.md`
2. `docs/00-project/FINAL_DESIGN_BLUEPRINT.md`
3. `docs/09-validation/VALIDATION_0_5_FINAL.md`
4. `docs/02-harness/STUDIO_ORCHESTRATION_V2.md`
5. `docs/02-harness/HARNESS_ARCHITECTURE.md`
6. `docs/03-content/CONTENT_SYSTEM.md`
7. `docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`
8. `docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`
9. `docs/06-production/AUDIO_POST_SYSTEM.md`
10. `docs/01-discovery/FULL_STUDIO_BLIND_SPOT_SWEEP.md`
11. `docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md`
12. `docs/10-reuse/ODDENGINE_REUSE_AUDIT.md`
13. `docs/00-project/REFERENCE_METHODS.md`
14. `docs/99-decisions/CHANGE_LOG.md`

If documents conflict, prefer the newest explicit addendum/decision and record consolidation work rather than silently choosing.

## 3. Project Goal

Civilization X-Ray is not a generic AI-video generator and not merely an architecture channel.

Goal:

> Explain the hidden mechanisms of structures, cities, historical engineering and civilization-scale infrastructure through evidence-linked long-form storytelling and explainable 3D/X-Ray visual grammar.

Default format: 8–15 minute long-form, topic-dependent.

Core question for every episode:

> What invisible mechanism becomes understandable only when we visually open, section, trace, explode, reconstruct or simulate it?

## 4. Non-Negotiable Working Method

The user expects these methods to be treated as project operating law:

1. Blind-spot sweep before locking consequential decisions.
2. Pre-mortem / trap check before implementation planning.
3. Four design alternatives shown together for consequential design choices when the alternatives are genuinely distinct.
4. User intent / audience / success criteria interview before architecture lock — but never repeat questions already answered in repository/chat context.
5. Reference-first work: inspect relevant GitHub/open-source/video/script exemplars and extract principles rather than copying surfaces.
6. If work blocks or deviates from the plan, record where, why, impact and rollback path in `docs/99-decisions/CHANGE_LOG.md`.
7. Keep top-level working laws synchronized in `CLAUDE.md`.
8. Evidence before claiming PASS/completion.
9. Do not over-orchestrate; logical role does not imply one physical agent.
10. Do not start implementation unless the user explicitly authorizes it.

## 5. Meta-Prompting Law

Use the cycle:

`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

### Context Dump
Include:
- goal
- current decisions
- forbidden changes
- references
- input/output contract
- execution environment
- known failures

### Missing Context Check
Before executing a generated prompt, ask internally:
- What context is truly missing?
- What ambiguity materially changes the answer?
- What assumptions am I making?

Do not ask the user for information already available in repository/current context.
If a missing fact is not blocking, record the assumption and continue.

### Success Criteria
Every serious prompt/work order should have verifiable success criteria.

### Environment-Specific Conversion
- Goal prompt: include stop conditions.
- Coding/agent prompt: include file scope, constraints, forbidden areas, verification commands/evidence.
- Image prompt: include composition, subject, structure/material, style, lighting, lens/camera direction and continuity locks.
- Video prompt: include start/end state, camera intent/path, invariant elements, allowed motion, duration and continuity bridge.
- Research prompt: include source policy, research boundary, source hierarchy, contradiction handling and verification method.

### Output Review
Do not treat generation as completion. Evaluate against success criteria and issue PASS / REVISE / REJECT / ESCALATE.

## 6. Reference Repositories

Verified methodology references:

- `multica-ai/andrej-karpathy-skills`
  - assumptions, simplicity, scope control, evidence before completion
- `bradautomates/claude-video`
  - timestamp transcript + visual/frame analysis, sparse-to-dense long-video analysis
- `obra/superpowers`
  - architecture discovery, brainstorming/design approval gates, written plans
- `Egonex-AI/Understand-Anything`
  - current lineage of the former `Lum1104/Understand-Anything`; relationship/dependency understanding
- `rohitg00/agentmemory`
  - persistent/retrievable memory, failure learning, context selection

Use `docs/00-project/REFERENCE_METHODS.md` for exact adopt/do-not-adopt boundaries.

Reference rule by task domain:
- software/system implementation → comparable GitHub/open-source code/harness
- documentary/video system → comparable video, script, production and prompt systems
- if this were a novel project → comparable novels/genre structures are the “reference code” equivalent

## 7. Existing Internal Reuse Sources

### `storm-credit/askanything_video_generator`
Use only the selected infrastructure patterns documented in `ASKANYTHING_REUSE_AUDIT.md`:
- Google client/provider boundary
- Veo operation lifecycle
- polling/retry/download
- quota/provider-health ideas
- media normalization
- bounded concurrency/cache
- cost-accounting patterns
- headless Blender execution pattern

Do not inherit Shorts-specific editorial/camera routing.

### `storm-credit/oddengine`
Use only the selected contracts documented in `ODDENGINE_REUSE_AUDIT.md`:
- executable artifact gates
- explicit shot continuity bridge
- durable prompt/reference provenance

Do not import its MV ontology, fixed stage pipeline, character-centric schema, fixed shot counts or exact model-routing matrix.

## 8. Current Studio Architecture

Top-level responsibility domains:

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

Visual hierarchy:

```text
Project Orchestrator
        ↓
Video Director
   ├─ Blender Spatial & Camera Specialist
   ├─ Veo Cinematic Camera Specialist
   └─ 2D Motion / Compositing capability
        ↓
Independent Visual QA
```

Blender owns deterministic spatial truth/camera where topology is explanatory evidence.
Veo owns cinematic generative reconstruction/people/atmosphere/bridge shots where exact topology is not the evidence.
Higgsfield is not a required dependency.

Music is a specialist responsibility inside Audio & Post, not a separate top-level orchestra.

## 9. Current Harness

Selected topology:

> **Stage-Gated Artifact Blackboard + Thin Director**

Effective Phase 1 physical core artifacts after Validation 0.5:
1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Keep logical distinctions inside these artifacts; split new physical files only when complexity proves the need.

## 10. Current No-Code Blind Spots / Remaining Work

Architecture is considered complete, but the following are still valuable:

- direct frame + timestamp transcript reverse-engineering of a 10-video benchmark corpus when media access permits
- update observed camera/action frequencies from real benchmark evidence
- one full-studio paper run through Editorial → Visual → Audio/Post → Release using the latest V2 contracts
- stale/dependency propagation check after a deliberate script revision
- verify executable-gate requirements for future Phase 1 artifacts
- consolidate any stale Phase 0 wording that conflicts with Validation 0.5

These may refine contracts but should not trigger wholesale architecture redesign without evidence.

## 11. Critical Stop Conditions

STOP / ESCALATE instead of proceeding when:
- a factual claim cannot be verified enough for the intended certainty
- exact geometry is required but evidence cannot support it
- rights/provenance is unresolved for a publish-bound asset
- a new design would silently invalidate a locked artifact
- expensive generation is requested before its upstream gate passes
- implementation would begin without explicit user authorization

Do not stop merely because a non-critical detail is unknown; record a bounded assumption and continue.

## 12. Paste-Ready Claude Bootstrap Prompt

Use the following as the first prompt in Claude Code if needed:

```text
GitHub 저장소 `storm-credit/civilization-xray`의 현재 main을 기준으로 이전 작업을 이어서 진행해.

중요: 이전 대화 내용을 추측하지 말고 저장소를 정본으로 읽어라.
먼저 다음 파일을 반드시 확인해:
- CLAUDE.md
- docs/00-project/FINAL_DESIGN_BLUEPRINT.md
- docs/09-validation/VALIDATION_0_5_FINAL.md
- docs/02-harness/STUDIO_ORCHESTRATION_V2.md
- docs/02-harness/HARNESS_ARCHITECTURE.md
- docs/03-content/CONTENT_SYSTEM.md
- docs/04-script/SCRIPT_VISUAL_GRAMMAR.md
- docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md
- docs/06-production/AUDIO_POST_SYSTEM.md
- docs/01-discovery/FULL_STUDIO_BLIND_SPOT_SWEEP.md
- docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md
- docs/10-reuse/ODDENGINE_REUSE_AUDIT.md
- docs/00-project/REFERENCE_METHODS.md
- docs/99-decisions/CHANGE_LOG.md
- docs/00-project/CLAUDE_HANDOFF.md

현재 상태는 Phase 0 architecture + Validation 0.5 설계 검증까지 완료됐고 구현은 시작하지 않았다.
사용자가 별도로 구현을 명시 승인하기 전까지 코드/API/앱 스캐폴딩/자동화 구현을 하지 마라.

작업 원칙:
1. 맹점 훑기 필수.
2. 구현 계획 전에 pre-mortem/함정 체크.
3. 중요한 설계 결정은 실제로 구분되는 4안을 한눈에 비교.
4. 사용자 의도/주사용자/성공조건을 확인하되 이미 저장소에 답이 있는 질문은 다시 묻지 말 것.
5. 유사 GitHub/영상/스크립트 레퍼런스를 먼저 조사하고 표면을 복사하지 말고 원리를 추출.
6. 계획과 달라지면 위치/이유/영향/rollback을 CHANGE_LOG.md에 기록.
7. 프로젝트 최상위 규칙이 바뀌면 CLAUDE.md도 동기화.
8. 완료/PASS는 근거가 있을 때만 선언.
9. logical role과 physical agent 수를 혼동하지 말고 과설계 금지.
10. 사용자가 자동 진행을 원하므로 비차단 불확실성은 가정을 기록하고 계속 진행. 정말 결과를 바꾸는 누락 정보만 질문.

메타 프롬프팅:
Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn.
각 prompt/work order에는 성공조건과 실행환경별 제약/중지요건을 포함해라.

방법론 레퍼런스:
- multica-ai/andrej-karpathy-skills
- bradautomates/claude-video
- obra/superpowers
- Egonex-AI/Understand-Anything (former Lum1104 lineage)
- rohitg00/agentmemory

내부 재사용 레퍼런스:
- storm-credit/askanything_video_generator: Veo/Google provider infrastructure 등 선택적 재사용
- storm-credit/oddengine: executable gates, continuity bridge, prompt/reference provenance만 선택적 재사용
각각 docs/10-reuse의 audit 문서를 우선해라.

첫 행동:
A) 현재 main 상태와 위 문서들의 충돌/낡은 상태표시를 점검하고,
B) 방금 나열한 작업 원칙이 실제 설계에 누락 없이 반영됐는지 compliance audit을 수행한 다음,
C) 새로운 근거가 없는 한 기존 Stage-Gated Artifact Blackboard + Thin Director / 4-orchestra 구조를 유지하고,
D) 남아 있는 no-code validation을 자동으로 계속 진행해라.

막히면 계획을 조용히 바꾸지 말고 CHANGE_LOG.md에 이유와 영향을 기록해라.
계획만 말하고 멈추지 말고, 현재 허용된 no-code 설계/검증 범위 안에서는 실제 문서 수정·검수·커밋/PR까지 진행해라.
```

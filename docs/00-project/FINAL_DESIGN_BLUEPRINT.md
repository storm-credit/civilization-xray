# Civilization X-Ray — Final Design Blueprint

Status: **Design complete / implementation not started**

## 1. Product Definition

Civilization X-Ray는 건축·도시·역사·인프라를 소재로 삼되, 소재 자체를 소개하는 채널이 아니다.

> **인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 3D/X-Ray 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부한다.**

Primary audience:
- 한국 일반 지식 시청자
- 공학 전공 지식 없이 이해 가능
- 미래 글로벌 확장을 고려한 visual-first 설계

Default format:
- 8–15분 롱폼
- 주제에 따라 가변
- Shorts는 핵심 설명 장면의 파생물이지 주 포맷이 아님

---

# 2. Strategic Positioning

Selected umbrella:
**Hidden Mechanisms of Civilization / 문명의 숨은 구조**

Content pillars:
1. Structures
2. Hidden Cities
3. Historical Engineering
4. Movement Systems
5. Mega Infrastructure
6. Failure X-Ray

Hard topic rule:
> “이 영상에서 X-Ray로 보여줄 보이지 않는 원리는 무엇인가?”

답할 수 없으면 주제 reject.

---

# 3. Content Grammar

Four episode types:
1. Mechanism Mystery
2. Construction Impossible
3. System Journey
4. Failure X-Ray

기본 script spine:
1. visual contradiction
2. question lock
3. scale/constraint
4. wrong intuition
5. first X-Ray reveal
6. mechanism chain
7. historical/human constraint
8. stress test/counterfactual
9. reassembly
10. payoff
11. residual wonder

모든 영상에 같은 순서를 기계적으로 강제하지 않고 episode grammar에 맞게 조정한다.

---

# 4. Core Intellectual Property

이 프로젝트에서 가장 중요한 장기 자산은 모델이나 특정 프롬프트가 아니다.

핵심 자산:

## A. Script ↔ Visual Grammar
- 문장 종류
- 설명 목적
- visual action
- camera action
- evidence level
- reveal timing

## B. Hero Object / Spatial Continuity System
- canonical structure
- hard/soft/free locks
- axis/orientation
- cutaway/explode/reassembly

## C. Claim Provenance Graph
`source → claim → narration → visual representation`

## D. Channel DNA
- topic score
- hook/payoff patterns
- visual language
- pacing
- post-publish learnings

## E. Failure Memory
- 모델/프롬프트/shot 실패 패턴
- 원인
- 복구법

---

# 5. Visual Direction

Selected:
**Documentary Hybrid 3D**

결합:
- cinematic establishing/reconstruction
- clean technical 3D explainer
- controlled X-Ray signature language

Geometry policy:
- topology가 설명의 근거이면 geometry/depth-backed 접근 우선
- 분위기/역사 장면/비핵심 B-roll은 generative AI 적극 활용

Visual truth levels:
- R0 documented
- R1 strong engineering inference
- R2 plausible reconstruction
- R3 illustrative

화면의 확신이 evidence의 확신보다 높아지지 않게 한다.

---

# 6. Production Philosophy

Selected:
**Hybrid Stage-Gated Production**

Lifecycle:

```text
Topic
 ↓
Research / Claims
 ↓
Story Design
 ↓
Script ↔ Visual Map
 ↓
Hero Object / Visual Bible
 ↓
Low-cost Previs
 ↓
High-cost Production
 ↓
Assembly
 ↓
Independent QA
 ↓
Publish
 ↓
Learning Capture
```

핵심 경제 원칙:
> Cheap reasoning first, expensive pixels last.

---

# 7. Harness Architecture

Selected:
**Stage-Gated Artifact Blackboard + Thin Director**

Why:
- 롱폼 상태를 단일 agent context에 넣지 않기 위해
- source/claim/script/visual lineage를 보존하기 위해
- expensive generation 전에 gate로 차단하기 위해
- rollback과 재현성을 확보하기 위해
- 모델/vendor 변경에 대비하기 위해

Director 역할:
- stage/state
- budget
- gate transition
- retry/rollback/escalation
- human approval

Director가 직접 “진실”을 독점하지 않는다.

---

# 8. Logical Capabilities

Physical agent count는 미확정.

Logical responsibilities:
1. Director / Orchestrator
2. Topic Strategy
3. Research Synthesis
4. Claim Verification
5. Narrative Architecture
6. Script–Visual Architecture
7. Asset / Spatial Architecture
8. Shot Architecture
9. Previs Evaluation
10. Production Execution
11. Continuity Review
12. Fact / Provenance Review
13. Editorial Review
14. Rights / Reconstruction Review

Phase 1에서는 일부를 합칠 수 있다.
역할을 합치더라도 rubric/authority boundary는 유지한다.

---

# 9. Core Artifacts

1. Topic Brief
2. Research Dossier
3. Claim Ledger
4. Beat Map
5. Narration Script
6. Script ↔ Visual Map
7. Hero Object Bible
8. Shot Spec Pack
9. Previs Pack
10. Generation Manifest
11. QA Reports
12. Episode Run Ledger

Artifact 수는 구현 전 paper walkthrough에서 YAGNI 검토 후 줄일 수 있다.

---

# 10. Quality Architecture

Weighted scorecard:
- Factual Integrity 15
- Claim Provenance 10
- Central Question & Payoff 10
- Script Clarity 10
- Script ↔ Visual Alignment 15
- Spatial Continuity 15
- Visual Explanatory Value 10
- Long-form Coherence 5
- Repeatability 5
- Cost/Human Burden 5

Final candidate threshold:
- total >= 80
- Fact / Alignment / Continuity >= 4/5
- hard fail = 0

실제 threshold는 pilot data로 보정.

---

# 11. Human-in-the-Loop

Initial Season:
1. Topic Lock
2. Claim Lock
3. Script Lock
4. Visual Bible Lock
5. Previs / expensive generation lock
6. Final Publish

반복적으로 수정 없이 통과하는 low-risk gate는 이후 자동화 후보.

---

# 12. Meta-Prompt System

Universal prompt envelope:
- Role
- Goal
- Context
- Input artifacts
- Constraints
- Output contract
- Success criteria
- Evidence requirements
- Stop/escalation conditions
- Self-check

Prompt workflow:
`Context Dump → Missing Context → Refine → Execute → Evaluate → Learn`

특정 output type에 맞춰 prompt compiler를 둔다.
- Research
- Script
- Script↔Visual
- Image
- Video
- Review

---

# 13. Reference Reverse Engineering

Initial benchmark:
- anchor reference 포함 10편
- timestamp transcript + frames
- 전체 sparse pass + 중요한 구간 dense analysis

Analyze:
- hook
- beat
- script sentence class
- visual action
- camera
- spatial state
- reveal timing
- continuity
- sound
- evidence/reconstruction

Output:
- channel constants
- episode-type rules
- one-off flourishes
- learn / do-not-copy separation

공개 근거 없는 툴 추정은 observation과 분리.

---

# 14. Major Risks Incorporated into Design

Critical/high risks:
- AI topology drift
- fake precision
- source echo chamber
- late-stage expensive failure
- identity dilution
- visual repetition
- premature automation
- Director context bloat
- vendor lock-in
- regeneration cost spiral
- encyclopedic scripts
- decorative visuals
- reference over-copying

각 risk는 gate/artifact/reviewer/budget/stop policy에 반영됨.

---

# 15. Model / Vendor Policy

현재 특정 모델을 표준으로 확정하지 않는다.

Harness는 capability를 요구한다.

예:
- timestamp transcription
- reference-conditioned image
- object-consistent video
- deterministic geometry/camera
- TTS
- compositing

구현 시 capability benchmark 후 provider를 연결한다.

---

# 16. Phase Boundaries

## Phase 0 — Design
**COMPLETE at architecture level.**

Outputs:
- constitution
- strategic decisions
- content system
- script/visual grammar
- visual system
- risk register
- production system
- quality system
- meta-prompt system
- harness architecture

## Validation 0.5 — No-code empirical validation
Before implementation:
1. 10-video reference corpus analysis
2. 3 pilot episode paper walkthroughs
3. artifact pruning
4. design corrections / change log

No implementation code required.

## Phase 1 — Minimal Supervised Prototype
**NOT STARTED.**

Goal later:
- one episode through the artifact/gate workflow
- minimal agent count
- no multi-language
- no autonomous publishing

## Phase 2 — Production Harness
Only after Phase 1 evidence.

## Phase 3 — Automation / Scale
Only after repeated quality and cost evidence.

---

# 17. Explicit Non-Decisions

아직 정하지 않은 것:
- programming language
- agent framework
- database
- vector database
- memory product
- video/image vendor
- TTS vendor
- Blender vs alternative geometry tooling implementation
- web UI
- cloud platform
- exact number of agents
- deployment architecture

이들을 지금 정하는 것은 premature implementation이다.

---

# 18. Design Completion Statement

Civilization X-Ray의 설계는 이제 “AI 영상 만들기” 수준이 아니라 다음을 포함한다.

- 무엇을 다룰지
- 어떤 질문을 선택할지
- 어떻게 대본을 구성할지
- 문장을 화면으로 어떻게 변환할지
- 어떤 컷은 실제 공간 구조가 필요한지
- 사실과 재구성을 어떻게 구분할지
- 어떤 단계에서 어떤 artifact를 넘길지
- 누가 무엇을 검증할지
- 어디서 되돌아갈지
- 비용을 어디서 막을지
- 무엇을 기억할지
- 하네스가 왜 이 형태여야 하는지

따라서 다음 행동은 코딩이 아니다.

> **Validation 0.5: 실제 레퍼런스 10편 역설계 + 3개 파일럿을 종이 위에서 끝까지 흘려보며 설계의 허점을 찾는 것.**

이 validation에서 설계가 바뀌면 `CHANGE_LOG.md`에 위치/이유/영향을 기록한 뒤에만 Phase 1 구현으로 이동한다.

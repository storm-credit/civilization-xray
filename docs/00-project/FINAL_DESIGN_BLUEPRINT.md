# Civilization X-Ray — Final Design Blueprint

Status: **ARCHITECTURE / CONTRACT DESIGN CLOSED**  
Implementation: **NOT STARTED / NOT AUTHORIZED**  
Current empirical status: see `docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md`.

This file is the consolidated design blueprint. When an older discovery document conflicts with Closure 0.6 or a newer explicit addendum, the newer closure/addendum is authoritative.

## 1. Product Definition

Civilization X-Ray는 건축·도시·역사·인프라를 소재로 삼되, 소재 자체를 소개하는 채널이 아니다.

> **인류가 만든 거대한 구조와 시스템의 보이지 않는 원리를, 정교한 X-Ray/단면/흐름/재구성 시각언어와 검증 가능한 롱폼 스토리텔링으로 해부한다.**

Primary audience:
- 한국 일반 지식 시청자
- 공학 전공 지식 없이 이해 가능
- 미래 글로벌 확장을 고려한 visual-first 설계

Default format:
- 8–15분 롱폼
- 주제에 따라 가변
- Shorts는 파생 포맷이지 주 포맷이 아님

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
> **“이 영상에서 X-Ray로 보여줄 보이지 않는 원리는 무엇인가?”**

답할 수 없으면 주제 reject.

---

# 3. Content Grammar

Four episode types:
1. Mechanism Mystery
2. Construction Impossible
3. System Journey
4. Failure X-Ray

기본 script spine:
1. visual contradiction / curiosity
2. question lock
3. scale / constraint
4. wrong intuition
5. first reveal
6. mechanism chain
7. historical / human constraint
8. stress test / counterfactual
9. reassembly
10. payoff
11. residual wonder

모든 영상에 같은 순서를 기계적으로 강제하지 않는다. 실제 grammar는 episode type에 맞게 선택한다.

10-video transcript/text corpus에서 확인된 대표 hook family:
- contradiction
- comparison anomaly
- invisible process
- incompatible constraints
- familiar icon / forgotten impossibility

정확한 카메라 빈도·컷 길이·음악 타이밍은 direct frame/timeline evidence 없이는 추정하지 않는다.

---

# 4. Core Intellectual Property

특정 모델이나 프롬프트보다 다음이 장기 자산이다.

## A. Script ↔ Visual Grammar
- sentence / narration intent
- explanatory objective
- visual action
- camera action
- evidence / reconstruction level
- reveal timing

## B. Spatial / Asset Continuity System
- canonical spatial definition
- object | component | system scope
- hard / soft / free locks
- axis / orientation
- cutaway / explode / reassembly
- semantic anchors
- optional behavioral/state invariants for stateful systems

## C. Claim Provenance Graph
`source → claim → story/narration → visual/audio/package`

## D. Channel DNA
- topic score
- hook/payoff patterns
- visual language
- pacing lessons
- audio language
- post-publish learnings

## E. Failure Memory
- tool/model/prompt/shot failure signature
- cause
- failed attempts
- successful recovery
- applicable conditions

---

# 5. Visual Direction

Selected:
**Documentary Hybrid 3D**

Combination:
- cinematic establishing / reconstruction
- deterministic technical 3D
- 2D diagrams / maps / flow explanation
- controlled X-Ray signature language

Routing law:
- topology / position / orientation가 설명의 증거이면 Blender/결정론적 2D 우선
- 지도·수치·흐름·상태는 2D를 first-class medium으로 사용
- 사람·날씨·역사 분위기·cinematic bridge는 generative video 후보
- generated media가 factual authority를 대체하지 않음

Visual truth / scale treatment:
- reconstruction levels: R0–R3
- scale: TRUE_SCALE | SCHEMATIC | EXAGGERATED_FOR_EXPLANATION

화면의 확신이 evidence의 확신보다 높아지지 않게 한다.

---

# 6. Production Philosophy

Selected:
**Hybrid Stage-Gated Production**

```text
Topic / Episode Brief
 ↓
Evidence / Claims
 ↓
Story
 ↓
Visual Plan ↔ Spatial / Asset Bible
 ↓
Low-cost Previs
 ↓
Production Pack / High-cost Production
 ↓
Audio / Picture Assembly
 ↓
Independent QA
 ↓
Release Decision
 ↓
Learning Capture
```

핵심 경제 원칙:
> **Cheap reasoning first, expensive pixels last.**

Narration unit count는 generated-shot count가 아니다. 같은 explanatory objective를 공유하면 하나의 visual work order로 묶는다.

---

# 7. Studio & Harness Architecture

Top-level studio:

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

Selected harness:
> **Stage-Gated Artifact Blackboard + Thin Director**

Director owns:
- stage / state
- gate transitions
- artifact version authority
- budget
- retry / rollback / escalation
- human approval state

Director does NOT own factual truth or every specialist artifact's content.

---

# 8. Responsibility Model

Logical capability ≠ 반드시 하나의 physical agent.

Core responsibility families:
1. Project Orchestrator
2. Topic / Editorial Strategy
3. Research
4. Independent Claim Verification
5. Narrative / Script
6. Script ↔ Visual Architecture
7. Video Direction
8. Blender Spatial & Camera
9. Generative Cinematic Video
10. 2D Motion / Compositing
11. Independent Visual QA
12. Narration / TTS
13. Music / Sound Design
14. Picture Edit / Mix / Caption
15. Packaging / Release
16. Fact / Rights / Quality Review
17. Analytics / Learning

실제 physical agent 수는 구현 시 context, authority, parallelism, retry/cost evidence를 보고 최소한으로 결정한다.

---

# 9. Seven Core Physical Artifacts — LOCKED FOR PHASE 1 PLANNING

Validation 0.5에서 초기 12 logical artifacts를 7개 physical artifacts로 축약했고, Closure 0.6 및 동적-routing paper test에서 충분성을 재검증했다.

1. **Episode Brief**
2. **Evidence Pack**
3. **Story Pack**
4. **Visual Plan**
5. **Spatial / Asset Bible**
6. **Production Pack**
7. **Review & Run Ledger**

초기 logical concepts(Claim Ledger, Narration Script, Shot Spec, Generation Manifest, QA Report 등)는 사라진 것이 아니라 위 artifact 안의 section/child record로 유지될 수 있다.

새 8번째 default artifact는 실제 context/authority/version failure가 증명될 때만 추가한다.

Detailed contract:
- `docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`
- `docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`
- `docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`

---

# 10. Quality Architecture — CURRENT 100-POINT SCORECARD

Authoritative rubric: `docs/07-quality/QUALITY_SCORECARD.md`

Current weights:
- Q1 Factual Integrity — 12
- Q2 Claim Provenance — 8
- Q3 Central Question & Payoff — 9
- Q4 Script Clarity — 8
- Q5 Script ↔ Visual Alignment — 12
- Q6 Spatial / Structural Continuity — 12
- Q7 Visual Explanatory Value — 8
- Q8 Long-form Coherence — 6
- Q9 Narration & Audio Intelligibility — 8
- Q10 Edit / Cross-Media Sync — 5
- Q11 Rights / Provenance Integrity — 5
- Q12 Packaging Integrity — 3
- Q13 Production Repeatability & Cost — 4

Total = 100.

Final QA baseline:
- weighted total >= 80
- Q1, Q5, Q6, Q9, Q11 each >= 4/5
- hard fail = 0

Critical failure cannot be averaged away by a high total score.

---

# 11. Human-in-the-Loop

Initial supervised gates:
1. Topic Lock
2. Claims Lock
3. Script Lock
4. Visual / Spatial Lock
5. Previs / expensive production approval
6. Final Publish Approval

반복적으로 수정 없이 통과하는 low-risk gate만 이후 자동화 후보가 된다.

No autonomous publishing in the minimal prototype.

---

# 12. Meta-Prompt System

Universal prompt/work-order envelope:
- Role
- Goal
- Context / artifact versions
- Constraints / forbidden changes
- Input contract
- Output contract
- Success criteria
- Evidence / verification requirements
- Stop conditions
- Escalation rule
- Self / output review

Workflow:
`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

Verdict:
`PASS | REVISE | REJECT | ESCALATE | NOT VERIFIED`

---

# 13. Reference Reverse Engineering — CURRENT STATUS

Reference roles are separated rather than forcing one channel to be the entire benchmark.

Current evidence:
- selected 10-video transcript/text corpus: **PASS / 10 OF 10** at declared evidence levels
- direct frame/timeline corpus: **PARTIAL / UNOBSERVED GAPS**

Rules:
- transcript evidence may support hook/story/mechanism grammar
- text alone cannot support exact camera move, cut frequency, transition, shot duration or music timing claims
- short-form references cannot be used as evidence for 8–15 minute pacing

Authoritative references:
- `docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md`
- `docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md`

---

# 14. Major Risks Incorporated into Design

Critical/high risks include:
- AI topology drift
- fake precision
- source echo chamber
- late-stage expensive failure
- visual identity dilution / repetition
- premature automation
- Director context bloat
- vendor/model lock-in
- regeneration cost spiral
- encyclopedic scripts
- decorative visuals
- reference over-copying
- unresolved rights / AI disclosure
- repetitive/mass-produced inauthentic output
- stale downstream assets after upstream change
- secrets / credentials leakage

각 risk는 gate/artifact/reviewer/budget/stop policy에 반영한다.

---

# 15. Model / Vendor Policy

특정 provider/model을 프로젝트 헌법에 고정하지 않는다.

Current locked principles:
- Blender = deterministic spatial/camera backbone when spatial truth is evidence
- Google video generation = capability adapter behind current model registry
- historical `Veo Specialist` name must not imply permanent Veo-only lock
- TTS provider remains swappable behind Voice/Narration contract
- music provider remains swappable behind Audio Beat Map / cue contract
- Post owns final timeline
- provider/model/version/cost/terms are dated registry state and must be refreshed before implementation or material publish changes

Current capability snapshot:
- `docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md`

---

# 16. Phase Boundaries — CURRENT

## Phase 0 — Architecture Design
**COMPLETE**

## Validation 0.5 — No-code Architecture / Artifact Validation
**COMPLETE at design-validation level**

Completed:
- three representative paper walkthroughs
- 12 logical → 7 physical artifact pruning
- continuity/scale/2D refinements
- harness validation

## Design Closure 0.6 — Contract Closure
**COMPLETE**

Completed:
- seven field-level artifact contracts
- Camera & Transition Grammar v1
- Audio/Post Timeline Contract v1
- Venice full-studio 7-artifact paper run
- stale-propagation fault injection

## Empirical No-code Refinement
Current state:
- 10-video transcript/text corpus: PASS 10/10
- direct frame/timeline evidence: PARTIAL
- tool/provider capability snapshot: PASS / dated
- publish-rights / AI-disclosure snapshot: PASS / dated
- dynamic discrete-routing mechanism class: PASS ON PAPER

No additional paper pilot is justified without new evidence of an unrepresented mechanism-class failure.

## Phase 1 — Minimal Supervised Prototype
**NOT STARTED / NOT AUTHORIZED**

Only after explicit user authorization:
1. Implementation Readiness Review
2. runtime pre-mortem
3. four genuinely different minimal implementation scopes
4. fixed benchmark inputs / tool auditions
5. language/framework/storage choice
6. minimal supervised prototype implementation plan
7. only then code

## Phase 2 — Production Harness
Only after Phase 1 evidence.

## Phase 3 — Automation / Scale
Only after repeated quality, cost and reliability evidence.

---

# 17. Explicit Implementation Non-Decisions

Intentionally deferred until Implementation Readiness Review:
- Python vs TypeScript
- LangGraph / workflow framework vs direct orchestrator
- database choice
- vector database need
- memory product / persistence implementation
- final video model/provider routing thresholds
- final Korean TTS provider/voice
- final music provider/default density
- Blender Python package/module structure
- web UI
- cloud platform
- exact physical agent count
- deployment architecture

These are implementation choices, not missing architecture.

---

# 18. Design Completion / Freeze Statement

The design now covers:
- what the project explains
- how topics are selected
- how claims are sourced and verified
- how story and narration are structured
- how narration maps to explanatory visuals
- how spatial/state truth is preserved
- when Blender / 2D / generative video are routed
- how camera/transition/audio/post work
- which seven artifacts carry episode state
- who owns/reviews each responsibility
- how gates/retry/rollback/stale propagation work
- how rights/disclosure/package integrity are checked
- what is remembered and versioned
- how provider/model changes are isolated
- where automation must stop

Architecture/contract design is **FROZEN/CLOSED** unless new empirical or prototype evidence demonstrates a concrete failure in authority, context, provenance, stale propagation, rights/security, factual/visual integrity, or measurable quality/cost.

Without implementation authorization, do not create work merely to keep designing. Only direct empirical evidence, materially changed provider/platform policy, or a proven contract gap justifies further no-code modification.

When implementation is explicitly authorized, the next legitimate stage is:

> **Implementation Readiness Review → Minimal Supervised Prototype plan → implementation**

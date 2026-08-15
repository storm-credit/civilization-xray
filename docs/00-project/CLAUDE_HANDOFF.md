# Civilization X-Ray — Claude Continuation Handoff

Status: **Paste-ready / repository-first continuation guide**  
State date: **2026-08-15**

This document lets a new Claude / Claude Code session continue from repository truth without reconstructing prior chat history.

## 1. Repository & Current State

- Repository: `storm-credit/civilization-xray`
- Default branch: `main`
- Project: long-form documentary/explainer production system
- Architecture / contract design: **CLOSED**
- Implementation: **NOT STARTED / NOT AUTHORIZED**
- Harness: **Stage-Gated Artifact Blackboard + Thin Director**
- Studio: **4 responsibility orchestras + independent governance/shared services**
- Core episode artifacts: **7, locked for Phase 1 planning**
- Venice end-to-end paper run: **PASS ON PAPER**
- Dynamic discrete-routing baggage paper test: **PASS ON PAPER**
- 10-video transcript/text benchmark: **PASS / 10 OF 10**
- 10-video direct frame/timeline benchmark: **PARTIAL / unobserved gaps remain**
- Tool/provider capability snapshot: **validated 2026-08-15, volatile**
- YouTube AI disclosure/rights/inauthentic-content policy snapshot: **validated 2026-08-15, volatile**

The important distinction is:

> **The remaining uncertainty is empirical/runtime evidence, not missing architecture.**

Do not reopen the architecture merely because Python/TypeScript, workflow framework, DB, TTS provider, music provider or exact Google video model have not been selected. Those are deliberately deferred implementation choices.

---

## 2. First Read Order

Before making decisions, read these files in order:

1. `CLAUDE.md`
2. `docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md`
3. `docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md`
4. `docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`
5. `docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`
6. `docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`
7. `docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md`
8. `docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md`
9. `docs/02-harness/STUDIO_ORCHESTRATION_V2.md`
10. `docs/02-harness/HARNESS_ARCHITECTURE.md`
11. `docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`
12. `docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`
13. `docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md`
14. `docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md`
15. `docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md`
16. `docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md`
17. `docs/09-validation/AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md`
18. `docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md`
19. `docs/10-reuse/ODDENGINE_REUSE_AUDIT.md`
20. `docs/00-project/REFERENCE_METHODS.md`
21. `docs/99-decisions/CHANGE_LOG.md` and newest dated decision files

For a concrete 7-artifact example, read:
- `docs/11-design-closure/pilot-venice/01_EPISODE_BRIEF.md`
- `02_EVIDENCE_PACK.md`
- `03_STORY_PACK.md`
- `04_VISUAL_PLAN.md`
- `05_SPATIAL_ASSET_BIBLE.md`
- `06_PRODUCTION_PACK.md`
- `07_REVIEW_RUN_LEDGER.md`

If documents conflict, prefer the newest explicit addendum/decision and record consolidation instead of silently choosing.

---

## 3. Project Goal

Civilization X-Ray is not a generic AI-video generator and not merely an architecture channel.

> **Explain the hidden mechanisms of structures, cities, historical engineering and civilization-scale infrastructure through evidence-linked long-form storytelling and explainable X-Ray / section / flow / reconstruction visual grammar.**

Default format: 8–15 minute long-form, topic-dependent.

Core episode question:

> **What invisible mechanism becomes understandable only when we visually open, section, trace, explode, reconstruct or simulate it?**

---

## 4. Non-Negotiable Working Law

1. Blind-spot sweep before consequential decisions.
2. Pre-mortem / trap check before implementation planning.
3. Compare four genuinely distinct alternatives for consequential choices; do not manufacture four cosmetic variants.
4. Check user intent / primary user / success criteria, but never repeat questions already answered in repository/current context.
5. Reference-first work: inspect relevant GitHub/open-source/video/script/production exemplars and extract principles, not surface copies.
6. If blocked or deviating, record where, why, impact, reversibility and rollback.
7. Keep top-level laws in `CLAUDE.md` synchronized when the law itself changes.
8. Evidence before PASS/completion claims.
9. Logical role ≠ physical agent. Do not over-orchestrate.
10. No implementation until the user explicitly authorizes it.
11. Minimal change / blast-radius control.
12. No silent provider/model/data fallback.
13. Preserve reproducibility/resumability/provenance.
14. Retry requires causal input change; respect retry/cost ceilings.
15. Never commit plaintext secrets/credentials.
16. Propagate stale state only to actual downstream dependencies.
17. Definition of Done is an evidence bundle, not “file created.”

---

## 5. Meta-Prompting Law

Use:

`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

Every serious work order should include:
- goal
- relevant context/versions
- constraints / forbidden changes
- input contract
- output contract
- success criteria
- evidence/verification rule
- stop condition
- escalation rule
- self/output review

Environment conversion:
- Goal prompt → stop condition
- Coding/agent prompt → file scope, constraints, forbidden areas, verification/evidence
- Image prompt → composition, subject, structure/material, style, lighting, lens/camera, continuity locks
- Video prompt → start/end state, camera intent/path, invariants, allowed movement, duration, continuity bridge
- Research prompt → source policy, scope, source hierarchy, contradiction handling, verification method

Verdict vocabulary:
`PASS | REVISE | REJECT | ESCALATE | NOT VERIFIED`

---

## 6. Closed Studio / Harness Architecture

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

Visual responsibility:

```text
Project Orchestrator
        ↓
Video Director
   ├─ Blender Spatial & Camera Specialist
   ├─ Generative Cinematic Video capability
   └─ 2D Motion / Compositing capability
        ↓
Independent Visual QA
```

The historical role name `Veo Cinematic Camera Specialist` must **not** be interpreted as a permanent Veo-only model lock. Current Google video model selection belongs behind a versioned capability adapter.

Selected harness:

> **Stage-Gated Artifact Blackboard + Thin Director**

Director owns phase/gate/budget/retry/escalation/version authority, not factual truth or every specialist artifact's content.

---

## 7. Seven Core Artifacts

1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Do not create an eighth default artifact unless a real episode proves a context/authority/versioning failure that these seven cannot represent.

Latest additive contracts:
- dynamic/stateful systems may use optional P5 behavioral/state invariants;
- existing continuity classes remain `OBJECT / SPATIAL / SEMANTIC / TEMPORAL`;
- P6 stores asset-level synthetic/provenance state;
- P7 stores final platform disclosure/authenticity/release state;
- no new Dynamic System Manifest or Disclosure Manifest is justified.

---

## 8. Current Empirical Results

### Reference corpus
- 10/10 selected transcript/text items analyzed at declared evidence level.
- Practical Engineering: mechanism/demo reference.
- The B1M: megaproject constraint/construction narrative reference.
- `신비한 건축사전`: Korean short-form packaging/hook/compressed-mechanism reference, **not** evidence for 8–15 minute pacing.
- direct video frame/timeline evidence remains partial; never invent camera-cut frequency, shot duration, music timing or visual frequency from transcript text.

Evidence-backed hook families:
- apparent contradiction
- comparison anomaly
- invisible ongoing process
- incompatible constraints
- familiar icon / forgotten impossibility

### Mechanism-class coverage
No-code tests now cover:
- static/spatial hidden structure — Venice
- continuous flow/system journey — aqueduct
- construction/alignment geometry — tunnel
- failure/stress/counterfactual grammar — reference corpus + existing design
- dynamic discrete identity/state/routing — airport baggage

Current evidence does **not** justify another paper pilot merely to continue design work.

### Tool/provider snapshot
As of the dated snapshot:
- Blender remains the deterministic spatial/camera backbone.
- Google video remains behind a capability adapter; do not hardcode one permanent default model from old AskAnything assumptions.
- Korean TTS is feasible, but final provider requires implementation-time A/B audition.
- generated music is feasible, but final provider and density require pilot audition.
- Post remains final timeline authority.

### Publish/rights snapshot
- asset-level provenance and platform-level AI disclosure are different controls.
- realistic generated reconstructions of real places/events and AI-generated music are current YouTube disclosure candidates/requirements per the dated validation.
- required disclosure is not itself a monetization failure.
- repetitive/mass-produced inauthentic content remains a monetization risk regardless of AI use.
- refresh policy before implementing publication automation.

---

## 9. Internal Reuse Boundaries

### `storm-credit/askanything_video_generator`
Reuse only audited infrastructure patterns such as:
- Google client/provider boundary
- generation request/poll/download/retry lifecycle
- quota/provider-health ideas
- media normalization
- bounded concurrency/cache
- cost accounting
- headless Blender execution pattern

Do not inherit:
- Shorts emotion/format routing
- fixed duration/aspect assumptions
- old model IDs/prices as current truth
- silent cross-provider fallback

### `storm-credit/oddengine`
Reuse only:
- executable artifact integrity gates
- explicit continuity bridge
- durable prompt/reference provenance

Do not import its MV ontology, fixed pipeline, fixed shot count, character schema or provider-routing matrix.

---

## 10. What Is Actually Left Before Coding

With current available evidence, **valuable architecture/design expansion is exhausted**.

Remaining no-code work is conditional, not mandatory busywork:

1. **Direct frame/timeline evidence** for the 10-video corpus — only when actual video frames are directly observable.
2. Refresh volatile provider/tool/platform policy snapshots when implementation/publishing decisions approach.
3. Audit another external repository only if it plausibly closes a known gap.
4. Run another paper episode only if new evidence demonstrates an unrepresented mechanism/contract failure.

Do not fill the gap by inventing:
- new orchestras
- new default agents
- new core artifacts
- DB/vector DB design
- dashboard/UI design
- cloud/deployment design
- language/framework decisions
- arbitrary additional pilots

Those would be premature or overengineering.

---

## 11. What Happens When the User Finally Authorizes Coding

Do **not** jump directly into code.

First perform an **Implementation Readiness Review**:

1. re-read current main and empirical status;
2. implementation pre-mortem;
3. compare four genuinely distinct minimal implementation scopes;
4. define fixed benchmark inputs for Blender / video / TTS / music auditions;
5. choose Python vs TypeScript, direct orchestrator vs framework, storage/database, physical agent count only against closed contracts and measured needs;
6. verify current official provider/model/API/pricing/quota terms again;
7. write a minimal supervised prototype implementation plan;
8. only then code.

Initial implementation must prove the smallest path, not build the whole autonomous studio at once.

Implementation decisions intentionally still open:
- Python vs TypeScript
- direct orchestrator vs LangGraph/other workflow framework
- SQLite/Postgres/other storage
- whether vector retrieval is needed at all
- physical agent count
- exact Blender Python package/API structure
- current Google video model routing
- final Korean TTS provider/voice
- final music provider

These are **not missing design**.

---

## 12. Paste-Ready Claude Bootstrap Prompt

```text
GitHub 저장소 `storm-credit/civilization-xray`의 현재 main을 정본으로 이전 작업을 이어서 진행해.

먼저 반드시 읽어:
1. CLAUDE.md
2. docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md
3. docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md
4. docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md
5. docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md
6. docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md
7. docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md
8. docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md
9. docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md
10. docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md
11. docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md
12. docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md
13. docs/10-reuse/ODDENGINE_REUSE_AUDIT.md
14. docs/00-project/CLAUDE_HANDOFF.md

현재 상태:
- architecture/contract design CLOSED
- Stage-Gated Artifact Blackboard + Thin Director 확정
- 4 responsibility orchestras 확정
- 7 core artifacts 확정
- Venice end-to-end paper run PASS ON PAPER
- dynamic discrete-routing baggage paper test PASS ON PAPER
- transcript/text reference corpus 10/10 PASS
- direct frame/timeline corpus만 PARTIAL
- implementation NOT STARTED / NOT AUTHORIZED

중요:
사용자가 명시적으로 구현을 승인하기 전에는 코드/API/앱 스캐폴딩/agent runtime/deployment를 만들지 마라.
현재 증거로는 추가 architecture expansion이나 추가 paper pilot을 기본적으로 만들 이유가 없다.

작업법:
- 맹점 훑기
- 구현 전 pre-mortem
- consequential decision은 4개의 실제 대안 비교
- 이미 답이 있는 사용자 질문 반복 금지
- reference-first
- 최소 변경
- silent fallback 금지
- deviation은 위치/이유/영향/rollback 기록
- evidence before PASS
- Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn

남은 no-code 검증은 실제 새 근거가 있을 때만 진행해:
- 직접 관찰 가능한 frame/timeline evidence
- 변동성이 큰 provider/platform policy refresh
- 명확한 gap을 닫는 외부 repo audit

사용자가 구현을 승인하면 바로 코딩하지 말고 Implementation Readiness Review → 4개 최소 구현안 비교 → 도구/언어/저장소 선택 → minimal supervised prototype plan → 코딩 순서로 진행해.

계획이 달라지면 조용히 바꾸지 말고 결정 기록에 이유와 영향을 남겨.
```

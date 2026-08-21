# Civilization X-Ray — Claude Continuation Handoff

Status: **Paste-ready / repository-first continuation guide**  
State date: **2026-08-22**

This document lets a new Claude / Claude Code session continue from repository truth without reconstructing prior chat history.

## 1. Repository & Current State

- Repository: `storm-credit/civilization-xray`
- Default branch: `main`
- Project: long-form documentary/explainer production system
- Architecture / contract design: **CLOSED**
- Design Completion Gate: **PASS — PRE-CODE FREEZE**
- Project state: **DESIGN_COMPLETE / CODE_LOCKED**
- Implementation: **NOT STARTED / NOT AUTHORIZED**
- Harness: **Stage-Gated Artifact Blackboard + Thin Director**
- Studio: **4 responsibility orchestras + independent governance/shared services**
- Core episode artifacts: **7, locked**
- Venice end-to-end paper run: **PASS ON PAPER**
- Dynamic discrete-routing baggage paper test: **PASS ON PAPER**
- 10-video transcript/text benchmark: **PASS / 10 OF 10**
- 10-video direct frame/timeline benchmark: **PARTIAL / NON-BLOCKING**
- AI-history market moat: **PASS / mechanism-first identity reaffirmed**
- AniJam: **W0 optional supervised workbench candidate**

The critical distinction:

> **Design is complete. Coding is still prohibited.**

Design completion does not imply implementation authorization. A future explicit user instruction is required before any implementation work may begin.

---

## 2. First Read Order

Before making decisions, read these files in order:

1. `CLAUDE.md`
2. `docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md`
3. `docs/11-design-closure/DESIGN_COMPLETION_GATE_V1.md`
4. `docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md`
5. `docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`
6. `docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`
7. `docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`
8. `docs/11-design-closure/GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md`
9. `docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md`
10. `docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md`
11. `docs/03-content/CONTENT_SYSTEM.md`
12. `docs/04-script/SCRIPT_VISUAL_GRAMMAR.md`
13. `docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`
14. `docs/06-production/AUDIO_POST_SYSTEM.md`
15. `docs/07-quality/QUALITY_SCORECARD.md`
16. `docs/02-harness/HARNESS_ARCHITECTURE.md`
17. `docs/02-harness/STUDIO_ORCHESTRATION_V2.md`
18. `docs/09-validation/REFERENCE_TRANSCRIPT_CORPUS_V1.md`
19. `docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md`
20. `docs/09-validation/AI_HISTORY_MARKET_MOAT_VALIDATION_2026_08_22.md`
21. `docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md`
22. `docs/09-validation/ANIJAM_CAPABILITY_VALIDATION_2026_08_22.md`
23. `docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md`
24. `docs/09-validation/AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md`
25. `docs/10-reuse/ASKANYTHING_REUSE_AUDIT.md`
26. `docs/10-reuse/ODDENGINE_REUSE_AUDIT.md`
27. `docs/99-decisions/CHANGE_LOG.md` and newest dated decision files

For a concrete 7-artifact example, read `docs/11-design-closure/pilot-venice/`.

If documents conflict, prefer the newest explicit addendum/decision and record consolidation rather than silently choosing.

---

## 3. Project Goal / Market Identity

Civilization X-Ray is not:
- a generic AI-video generator;
- a world-architecture slideshow;
- an AI-history recreation/time-travel vlog channel;
- a generic megaproject chronology channel.

Core promise:

> **Explain the hidden mechanisms of structures, cities, historical engineering and civilization-scale infrastructure through evidence-linked long-form storytelling and X-Ray / section / flow / reconstruction visual grammar.**

Core episode question:

> **What invisible mechanism becomes understandable only when we visually open, section, trace, explode, reconstruct or simulate it?**

Market identity rule:

> **History is a context/pillar. Mechanism is the channel identity.**

Historical AI reconstruction is a production layer. The episode thesis must remain valuable even if the cinematic reconstruction shots are removed.

---

## 4. Non-Negotiable Working Law

1. Design before implementation.
2. **Design Completion PASS does not authorize coding.**
3. Coding requires a future explicit user authorization.
4. Blind-spot sweep before consequential decisions.
5. Runtime implementation planning requires pre-mortem first.
6. Compare four genuinely distinct alternatives for consequential choices.
7. Never repeat user questions already answered in repository/current context.
8. Reference-first; extract principles rather than copying surfaces.
9. Minimal change / blast-radius control.
10. `KEEP → PATCH → CUT → NEW DESIGN`; NEW DESIGN only with evidence.
11. No silent provider/model/data fallback.
12. Deep blackboard, small execution context.
13. Preserve provenance / resumability / version lineage.
14. Retry requires a causal input change.
15. Secrets/credentials never enter repo/prompt/artifact plaintext.
16. Field-aware stale propagation.
17. Evidence before PASS/completion claims.
18. Logical role ≠ physical agent.
19. Do not add agent/orchestra/artifact merely because a new tool/model appears.
20. Anti-template: reusable production grammar is allowed, interchangeable episode substance is not.

Meta-prompt loop:

`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

Verdicts:
`PASS | REVISE | REJECT | ESCALATE | NOT VERIFIED`

---

## 5. Closed Studio / Harness Architecture

```text
Project Orchestrator
│
├─ Editorial & Research Orchestra
├─ Visual Production Orchestra
├─ Audio & Post Orchestra
└─ Release & Learning Orchestra

Cross-cutting:
├─ Fact / Rights / Quality Governance
└─ Shared Asset / Memory / Provider Health Services
```

Visual responsibility:

```text
Project Orchestrator
        ↓
Video Director
   ├─ Blender Spatial & Camera Specialist
   ├─ Generative Cinematic Video capability
   │    ├─ Direct Provider Adapter(s)
   │    └─ Optional Supervised Workbench (AniJam W0 candidate)
   └─ 2D Motion / Compositing capability
        ↓
Independent Visual QA
```

Rules:
- Blender owns deterministic spatial truth when topology/orientation is evidence.
- 2D owns maps, diagrams, force/flow/state/routing explanation when clearer.
- Generative video owns cinematic context/reconstruction where exact topology is not factual authority.
- AniJam may execute approved Visual Work Orders but may not become Story/Visual/Spatial/Post authority.
- AniJam automatic scene breakdown is `NON-CANON` unless explicitly promoted into the correct upstream artifact.
- Post owns the final timeline.
- No named SaaS is mandatory.

Selected harness:

> **Stage-Gated Artifact Blackboard + Thin Director**

Director owns phase/gate/budget/retry/escalation/version authority—not factual truth or every specialist artifact's content.

---

## 6. Seven Core Artifacts

1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Do not create an eighth default artifact unless real evidence proves a context/authority/versioning failure that these seven cannot represent.

Latest additive semantics:
- dynamic/stateful systems may use optional P5 behavioral/state invariants;
- continuity remains `OBJECT / SPATIAL / SEMANTIC / TEMPORAL`;
- P6 stores generation/workbench/provenance state;
- P7 stores release/disclosure/authenticity state;
- workbench `NOT_EXPOSED` provider/model provenance is explicit and never guessed.

---

## 7. Current Empirical Results

### Reference / editorial
- selected transcript/text corpus: 10/10 complete at declared evidence level;
- direct frame/timeline evidence: partial and non-blocking;
- Practical Engineering: mechanism/demo/failure reference;
- The B1M: megaproject constraint/construction reference;
- `신비한 건축사전`: Korean hook/packaging/compressed-mechanism reference, not long-form pacing authority;
- AI-history recreation/time-travel channels: adjacent market, not umbrella identity.

### Mechanism-class coverage
No-code design tests cover:
- static/spatial hidden structure — Venice;
- continuous flow — aqueduct;
- construction/alignment — tunnel;
- failure/counterfactual logic;
- dynamic discrete identity/state/routing — airport baggage.

### Tool/provider
- Blender deterministic route supported conceptually; runtime performance deferred.
- direct video provider remains behind capability adapter.
- AniJam = W0 optional manual/assisted workbench; runtime API suitability not verified.
- Korean TTS feasible; final voice/provider deferred to audition.
- generated music feasible; final provider/density deferred to audition.

### Rights / platform
- asset provenance and upload-level disclosure are separate controls.
- realistic synthetic historical reconstruction requires disclosure review.
- repetitive/mass-produced/template-like AI content is a platform/authenticity risk.
- mechanism-specific evidence and non-interchangeable episodes are part of the defense.

---

## 8. What Is Actually Left

Design/architecture work is **complete for pre-code freeze**.

Remaining work is conditional empirical evidence, not a reason to keep designing:

- directly observable frame/timeline benchmark evidence;
- materially changed provider/platform policy refresh;
- supervised AniJam/tool audition without integration code;
- source/rights research for publish-bound assets;
- design PATCH only if real evidence breaks a current contract.

Do not fill time by inventing:
- new orchestras;
- new default agents;
- new core artifacts;
- DB/vector DB architecture;
- UI/dashboard/deployment design;
- language/framework choices;
- arbitrary paper pilots.

---

## 9. Coding Lock

Current authoritative state:

> **DESIGN_COMPLETE / CODE_LOCKED**

Until a future explicit user instruction authorizes implementation, do not create:
- application/runtime code;
- Python/TypeScript scaffold;
- LangGraph/agent framework setup;
- DB/vector DB implementation;
- Blender automation scripts;
- AniJam/Veo/Google/provider API integration;
- TTS/music integrations;
- publishing automation;
- UI/dashboard/deployment code.

Even after future implementation authorization, do not jump straight to code. First run:

> **Implementation Readiness Review → runtime pre-mortem → 4 minimal scopes → fixed tool auditions/technology choices → Minimal Supervised Prototype plan → code**

---

## 10. Paste-Ready Bootstrap Prompt

```text
GitHub 저장소 `storm-credit/civilization-xray`의 현재 main을 정본으로 이전 작업을 이어서 진행해.

먼저 읽어:
1. CLAUDE.md
2. docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md
3. docs/11-design-closure/DESIGN_COMPLETION_GATE_V1.md
4. docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md
5. docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md
6. docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md
7. docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md
8. docs/11-design-closure/GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md
9. docs/03-content/CONTENT_SYSTEM.md
10. docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md
11. docs/09-validation/AI_HISTORY_MARKET_MOAT_VALIDATION_2026_08_22.md
12. docs/09-validation/ANIJAM_CAPABILITY_VALIDATION_2026_08_22.md
13. docs/00-project/CLAUDE_HANDOFF.md

현재 상태:
- Architecture / contract design CLOSED
- Design Completion Gate PASS
- project state = DESIGN_COMPLETE / CODE_LOCKED
- Stage-Gated Artifact Blackboard + Thin Director 확정
- 4 responsibility orchestras 확정
- 7 core artifacts 확정
- mechanism-first channel identity 확정
- Venice / dynamic-routing paper tests PASS ON PAPER
- transcript/text reference corpus 10/10 PASS
- direct frame/timeline evidence만 PARTIAL / NON-BLOCKING
- AniJam = W0 optional supervised workbench candidate
- implementation NOT STARTED / NOT AUTHORIZED

가장 중요한 금지:
사용자가 미래에 명시적으로 구현을 승인하기 전에는 코드/API/Blender automation/DB/agent runtime/deployment를 만들지 마라.
Design Completion PASS를 구현 승인으로 해석하지 마라.

작업법:
- 맹점 훑기
- KEEP → PATCH → CUT → NEW DESIGN
- consequential decision은 실제 4안 비교
- 이미 답이 있는 사용자 질문 반복 금지
- reference-first
- 최소 변경
- deep blackboard, small context
- silent fallback 금지
- deviation은 이유/영향/rollback 기록
- evidence before PASS
- Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn

새 evidence가 없으면 설계를 더 늘리지 마라.
남은 no-code 작업은 직접 frame/timeline evidence, policy/provider refresh, supervised tool audition, source/rights research 정도뿐이다.

미래에 사용자가 구현을 승인하면 Implementation Readiness Review → runtime pre-mortem → 4개 최소 구현안 → tool audition/기술 선택 → Minimal Supervised Prototype plan → 코드 순서로 진행해.
```

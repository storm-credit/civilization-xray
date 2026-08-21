# Civilization X-Ray — CLAUDE.md

> 이 파일은 `civilization-xray`에서 AI 에이전트가 따라야 하는 최상위 작업 규칙이다.
> **현재 상태: Architecture / Contract Design CLOSED + Design Completion Gate PASS / PRE-CODE FREEZE.** `VX-PILOT-001` 베네치아 end-to-end paper run, stale propagation fault injection, dynamic discrete-routing baggage paper test, 10-video transcript/text benchmark, AI-history market moat validation 및 AniJam workbench routing 검증까지 반영되어 있다. 직접 frame/timeline benchmark는 PARTIAL이다. **Implementation은 NOT STARTED / NOT AUTHORIZED / CODE LOCKED**이며, 사용자가 미래에 명시적으로 구현을 승인하기 전까지 코드 작성, 앱 스캐폴딩, 자동화 구현, API 연동, Blender 스크립트, DB/agent framework, 배포 설정을 금지한다.

## 0. Continuation / Cross-Assistant Rule

이 저장소가 대화보다 우선하는 현재 상태의 정본이다.

다른 Claude/AI 세션에서 이어서 작업할 때:
- 먼저 `CLAUDE.md`, `docs/09-validation/EMPIRICAL_VALIDATION_STATUS.md`, `docs/11-design-closure/DESIGN_COMPLETION_GATE_V1.md`, `docs/11-design-closure/DESIGN_CLOSURE_0_6_FINAL.md`, `docs/00-project/CLAUDE_HANDOFF.md`, `docs/99-decisions/CHANGE_LOG.md` 및 최신 dated decision을 읽는다.
- artifact 계약이 필요하면 `docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`와 최신 additive contract를 읽는다.
- camera/transition 작업이면 `CAMERA_TRANSITION_GRAMMAR_V1.md`, audio/post 작업이면 `AUDIO_TIMELINE_CONTRACT_V1.md`를 읽는다.
- generative workbench/AniJam 관련이면 `GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md`와 `ANIJAM_CAPABILITY_VALIDATION_2026_08_22.md`를 읽는다.
- 사용자가 이미 답했거나 저장소에 명시된 질문을 다시 묻지 않는다.
- 정말 필요한 컨텍스트가 없고 그 누락이 의사결정/정확도에 materially 영향을 줄 때만 질문한다.
- 사용자가 “자동으로 계속 진행”을 요청한 상태라면, 비차단 가정은 명시적으로 기록하고 진행한다.
- 현재 설계와 충돌하는 새 결정을 내리면 기존 결정을 조용히 덮지 말고 `CHANGE_LOG.md` 또는 최신 dated decision에 위치/이유/영향/rollback을 남긴다.
- Architecture CLOSED 또는 Design Completion PASS를 구현 허가로 해석하지 않는다.
- 구현 허가가 없는 상태에서 구현으로 넘어가지 않는다.

## 1. Project Intent

Civilization X-Ray는 단순한 세계 건축물 소개 채널, AI 역사 재현 채널, AI 영상 생성기가 아니다.

핵심 가설:

> **인류가 만든 거대한 구조·도시·인프라·역사 기술의 보이지 않는 원리를, 정교한 X-Ray/단면/흐름/재구성 시각언어와 검증 가능한 롱폼 스토리텔링으로 설명한다.**

대상 영역은 건축, 도시, 토목, 교통, 역사 공학, 문명 인프라다. 실제 episode 선택은 현재 정본의 콘텐츠 포지셔닝/스코어 규칙을 따른다.

시장/역사 인접 규칙:
> **History is a context/pillar. Mechanism is the channel identity.**

AI 역사 재현, 타임트래블 vlog, cinematic history 자체는 umbrella가 아니다. 역사 장면은 숨은 구조/제약/흐름/물류/상태/실패 원리를 설명할 때 사용한다.

## 2. Non-Negotiable Working Rules

1. **Design before implementation**
   - 구현보다 브레인스토밍/설계/검증이 먼저다.
   - 현재 architecture/contract design은 닫혔고 `DESIGN_COMPLETION_GATE_V1`도 PASS했다. 새로운 근거 없이 다시 확장 설계하지 않는다.
   - 그러나 **Design Completion PASS ≠ coding permission**이다.
   - 구현으로 이동하려면 두 조건이 모두 필요하다:
     1. `DESIGN_COMPLETION_GATE = PASS`
     2. 미래 시점의 `USER_IMPLEMENTATION_AUTHORIZATION = EXPLICIT`
   - 현재 두 번째 조건이 없으므로 구현 디렉터리, 실행 스크립트, API 클라이언트, Blender 자동화, DB/agent framework, 자동화 코드를 만들지 않는다.

2. **User interview before architecture lock**
   - 사용자의 의도, 주사용자/시청자, 성공조건, 품질 기준, 자동화 수준, 비용/속도/정확도 우선순위를 확인한다.
   - 이미 대화나 정본 문서에서 답이 확인되는 질문은 반복하지 않는다.
   - 질문 없이 합리적으로 진행 가능한 비차단 항목은 가정을 기록하고 진행한다.

3. **Blind-spot sweep is mandatory**
   - consequential decision 전 콘텐츠, 팩트, 시각 일관성, 저작권, 비용, 모델 한계, 롱폼 연속성, 운영성, 평가 가능성, 공급망/API 의존성을 훑는다.

4. **Pre-mortem / trap check before implementation planning**
   - “3개월 뒤 실패했다면 왜 실패했는가?”를 가정하고 예방책, 탐지 신호, 중단/우회 기준을 붙인다.

5. **Four alternatives at consequential design decisions**
   - 채널 포지셔닝, 비주얼 언어, 제작 파이프라인, 하네스 구조, 중요한 release package처럼 실제로 다른 대안이 있을 때 4개 시안을 한눈에 비교한다.
   - 4안이 형식적 중복만 만들면 이유를 기록하고 생략할 수 있다.

6. **Reference-first, not imitation-first**
   - 유사 프로젝트, 오픈소스, 영상/스크립트 본보기를 조사한다.
   - 표면적 복제가 아니라 반복 가능한 원리, 인터페이스, 평가법을 추출한다.
   - 레퍼런스의 라이선스·출처·차용 범위를 기록한다.
   - 소프트웨어 작업 → 유사 GitHub 코드/하네스.
   - 콘텐츠 작업 → 유사 영상/대본/제작 문법.
   - 소설 프로젝트라면 “본보기 코드”에 해당하는 것은 유사 장르 작품/구조 분석으로 치환한다.

7. **Record deviations**
   - 원래 계획과 달라졌다면 어디서/왜/영향/되돌릴 수 있는지 기록한다.
   - `docs/99-decisions/CHANGE_LOG.md` 또는 dated decision에 남긴다.
   - 프로젝트 최상위 법이 바뀌면 `CLAUDE.md`도 동기화한다.

8. **Evidence before completion claims**
   - “완료”, “검증됨”, “통과”는 근거 없이 선언하지 않는다.
   - 상태 문자열만으로 gate를 통과시키지 않는다. 실제 artifact/version/evidence integrity가 있어야 한다.

### 2.1 Operational Hardening Rules

다음 규칙은 구현·리서치·콘텐츠 제작·에이전트 자동화 전반에 공통 적용한다.

9. **Minimal change / blast-radius control**
   - 목표를 달성하는 가장 작은 변경을 우선한다.
   - 관련 없는 파일, 계약, 프롬프트, 에이전트 구조를 함께 정리하거나 리팩터링하지 않는다.
   - 변경 전 `what changes / what must not change / affected downstream`을 명시한다.
   - 구조적 리팩터링은 기능 수정과 분리하고 별도 근거와 검증을 요구한다.

10. **No silent fallback**
   - 모델/API/도구/소스가 실패했을 때 다른 provider, 더 낮은 품질 경로, 오래된 캐시, 추정값으로 조용히 대체하지 않는다.
   - fallback이 허용되면 `무엇이 실패했는지 / 무엇으로 대체했는지 / 품질·비용·팩트 영향`을 기록한다.
   - fallback이 성공조건을 바꾸면 자동 진행하지 말고 `ESCALATE`한다.

11. **Reproducibility and resumability**
   - 중요한 결과는 chat context에만 존재하면 안 된다.
   - 입력 artifact/version, prompt/version, provider/model/tool version, 주요 설정, output identity를 재현 가능한 형태로 남긴다.
   - 긴 작업은 중간 실패 후 처음부터 전부 다시 하지 않고 last verified checkpoint에서 재개할 수 있어야 한다.
   - 동일 입력에 대한 재실행이 불필요한 중복 산출물을 만들지 않도록 idempotency를 지향한다.

12. **Retry / cost / time budget**
   - blind retry 금지. 재시도 전 실패 원인을 분류하고 최소 하나의 causal input을 바꾼다.
   - task/shot/stage마다 retry ceiling과 cost ceiling을 둘 수 있어야 한다.
   - 한도 초과 시 품질을 몰래 낮추지 말고 `ESCALATE` 또는 cheaper valid route로 명시적 reroute한다.
   - “이미 쓴 비용” 때문에 품질 미달 결과를 승인하지 않는다.

13. **Secrets / credentials / sensitive-data rule**
   - API key, service-account secret, access token, cookie, private credential을 저장소·프롬프트·로그·artifact에 평문으로 남기지 않는다.
   - secret 값 자체가 아니라 secret reference/환경변수 이름만 기록한다.
   - 외부 서비스로 보내는 context는 task에 필요한 최소 범위로 제한한다.
   - debug output에 credential 또는 불필요한 민감 데이터가 섞이지 않았는지 확인한다.

14. **Dependency-aware stale propagation**
   - upstream artifact가 바뀌면 downstream 전체를 무조건 폐기하거나, 반대로 아무것도 갱신하지 않는 두 극단을 피한다.
   - 변경된 field/claim/asset과 실제 dependency가 있는 downstream만 `STALE` 처리한다.
   - stale artifact는 재검증 전 publish/final gate에서 사용할 수 없다.
   - dependency 영향이 불명확하면 보수적으로 REVIEW 상태로 보내되 원인을 기록한다.

15. **Definition of Done = evidence bundle**
   - 완료는 “코드/문서/미디어를 만들었다”가 아니라 성공조건을 충족했다는 증거 묶음이다.
   - 작업 유형에 맞게 최소한 `outputs + validation result + unresolved risks + changed files/artifacts + next boundary`를 남긴다.
   - 테스트/검증을 실행하지 못했으면 PASS라고 쓰지 않고 `NOT VERIFIED`와 이유를 명시한다.
   - 사용자에게 보고하는 완료 상태와 저장소/run ledger의 상태가 서로 달라서는 안 된다.

16. **KEEP → PATCH → CUT → NEW DESIGN**
   - 새 근거가 생겨도 먼저 기존 구조로 해결 가능한지 본다.
   - `KEEP`: 기존 계약으로 해결.
   - `PATCH`: 필드/규칙의 작은 보강.
   - `CUT`: 불필요하거나 중복된 구조 제거.
   - `NEW DESIGN`: 위 셋으로 해결 불가능하고 실제 evidence가 있을 때만.
   - 새 모델/서비스/트렌드가 등장했다는 이유만으로 orchestra/agent/artifact를 추가하지 않는다.

17. **Deep Blackboard, small execution context**
   - 저장 구조/그래프는 깊어도 실제 specialist/workbench prompt는 최소 충분 context만 제공한다.
   - 전체 Evidence Pack/Story Pack/프로젝트를 모든 실행자에게 넣지 않는다.
   - approved work order + linked claims + relevant locks + success/stop conditions 중심으로 compile한다.

## 3. Meta-Prompting Protocol

기본 사이클:

`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

### 3.1 Context Dump
목표, 현재 결정, 금지사항, 참고자료, 입력/출력, 실행환경, 실패 사례를 충분히 제공한다.

### 3.2 Missing Context / Prompt Refinement
AI가 먼저 내부적으로 점검한다.
- 좋은 결과를 위해 어떤 컨텍스트가 더 필요한가?
- 무엇이 모호한가?
- 어떤 가정을 하고 있는가?

저장소/현재 대화에 이미 있으면 재질문하지 않는다. 성공조건을 materially 바꾸는 정보만 질문한다. 불필요한 지시/중복/충돌을 깎아낸다.

### 3.3 Success Criteria
serious prompt/work order마다 가능한 한 검증 가능한 성공조건을 붙인다.

예:
- 첫 30초 안에 핵심 질문/시청 이유/visual transformation이 나타난다.
- 사실 주장은 source/claim에 연결된다.
- 같은 구조는 여러 shot에서 동일 hard lock을 유지한다.
- 대본 핵심 설명마다 explanatory visual coverage가 있다.
- 다음 단계가 재해석 없이 산출물을 사용할 수 있다.

### 3.4 Environment-Specific Prompt Conversion
- Goal prompt: 목표 + **중지 조건**.
- Agent/coding prompt: 제약, 파일 범위, 변경 금지 영역, 검증 명령, 완료 증거.
- Image prompt: 구도, 피사체, 구조, 재질, 스타일, 조명, 렌즈/카메라 방향, continuity lock.
- Video prompt: 시작/종료 상태, 카메라 의도/경로, invariant, 허용 움직임, shot duration, continuity bridge.
- Research prompt: 조사 범위, 허용 출처, 1차/2차 출처 우선순위, 상충 자료 처리, 검증 방식.

### 3.5 Output Review
결과를 생성했다고 완료가 아니다.

최소 점검:
- 성공조건 충족?
- I/O 계약 준수?
- 근거 없는 완료 주장/가정?
- 정본/hard lock/권리/팩트 충돌?
- 다음 단계가 재해석 없이 사용 가능?
- 실패 원인과 causal input 변경이 명확?

Verdict: `PASS | REVISE | REJECT | ESCALATE | NOT VERIFIED`.

## 4. Design / Discovery History and Current Rule

기본 discovery flow:
1. Context dump
2. Project/user interview
3. Reference collection
4. Reference reverse-engineering
5. 4-way comparison
6. Brainstorming synthesis
7. Blind-spot sweep
8. Pre-mortem
9. Success criteria / quality bar
10. Harness-readiness gate
11. Harness 4안 비교
12. Harness contracts/state/memory/gates/failure recovery
13. Written design review
14. Design Closure / paper validations
15. Design Completion Gate
16. Future explicit implementation authorization
17. Implementation Readiness Review
18. Implementation plan
19. Only then implementation

현재 프로젝트는 1~15를 완료했다. **16은 아직 충족되지 않았다.** 새 세션에서 1~15를 처음부터 기계적으로 재수행하지 않는다.

## 5. Harness Is a First-Class Design Artifact

Selected topology:

> **Stage-Gated Artifact Blackboard + Thin Director**

Harness must preserve:
- orchestrator/director responsibility
- capability boundaries
- I/O contracts
- artifact/version/state
- source/evidence lineage
- quality gates/rejection loops
- human approval
- memory layers
- retry/fallback/escalation/stop conditions
- budget controls
- capability/model registry
- vendor swap boundary
- observability/run ledger
- prompt/script/visual versioning
- reproducibility
- rights/security/provenance

Closure and later additive validations confirmed this topology with Venice, dynamic routing, rights/disclosure and optional workbench cases. New evidence is required to change it.

## 6. Content-Specific Quality Principles

1. **Question-first**: 장소 소개보다 왜/어떻게 가능한가?
2. **Mechanism-first identity**: 역사/건축/도시는 소재다. 숨은 작동 원리가 채널 정체성이다.
3. **Script ↔ Visual Grammar**: 문장과 화면 행동의 연결이 핵심 자산.
4. **Structural continuity**: 같은 구조는 shot이 바뀌어도 같은 구조.
5. **Explain, not decorate**: 비주얼은 원인·구조·흐름·상태를 설명.
6. **Long-form continuity**: 개별 멋진 컷보다 정보·공간·스타일 연속성.
7. **Fact/visual separation**: 사실/추론/재구성 구분.
8. **No fake precision**: 자료 없는 내부 구조/수치 금지.
9. **Audio supports explanation**: narration meaning 우선, music/SFX는 지원.
10. **Release cannot escalate truth**: 제목/썸네일은 Evidence Pack보다 강한 주장을 할 수 없음.
11. **Narration unit ≠ shot count**: 같은 visual objective를 공유하면 묶는다. 생성 비용을 문장 수에 비례시키지 않는다.
12. **Representative ≠ universal**: 대표 기술/단면을 도시/시대 전체의 동일한 사실처럼 보이게 하지 않는다.
13. **History reconstruction is not the product**: AI 역사 재현 장면이 없어도 episode thesis가 살아 있어야 한다.
14. **Anti-template originality**: 제작 문법은 재사용 가능하지만 각 episode의 mechanism/evidence/payoff는 서로 바꿔 끼울 수 없어야 한다.

## 7. Reference Principles

방법론 참고 대상:
- `multica-ai/andrej-karpathy-skills`
- `bradautomates/claude-video`
- `obra/superpowers`
- `Egonex-AI/Understand-Anything` (former Lum1104 lineage)
- `rohitg00/agentmemory`

적용 질문:
- Karpathy Guidelines → 가정/범위/단순성/완료 증거
- Superpowers → 구현 전 설계/승인/gate
- claude-video → transcript + frame/scene 분석
- Understand-Anything → 관계/의존성 구조화
- agentmemory → 장기 기억/실패 학습/context retrieval

상세 adopt/do-not-adopt는 `docs/00-project/REFERENCE_METHODS.md`.

Internal reuse:
- `storm-credit/askanything_video_generator` → provider infrastructure 등 audit에서 승인한 부분만.
- `storm-credit/oddengine` → executable artifact gates, continuity bridge, prompt/reference provenance만.

Adjacent market/reference rule:
- `신비한 건축사전` → 한국형 hook/packaging/compressed mechanism reference.
- Practical Engineering → mechanism/demo/failure explanation reference.
- The B1M → megaproject constraint/narrative reference.
- AI history/time-travel/cinematic reconstruction → adjacent market signal; umbrella identity로 복제하지 않는다.

## 8. Change Protocol

계획 변경은 `docs/99-decisions/CHANGE_LOG.md` 또는 최신 dated decision에 기록:
- Date
- Previous decision
- New decision
- Trigger/evidence
- Why
- Impact
- Reversible / rollback
- Affected files/stages
- Follow-up validation

## 9. Current Boundary / Stop Condition

현재 design status:
- Strategic design: PASS
- Market/positioning moat: PASS / mechanism-first reaffirmed
- Content system: PASS
- Script system: PASS
- Visual architecture: PASS
- Risk/pre-mortem: PASS
- Harness architecture: PASS
- 7 core artifact contract: PASS / paper-tested
- Camera/transition grammar: PASS for pre-code freeze
- Audio/Post timeline contract: PASS for pre-code freeze
- End-to-end Venice paper run: PASS ON PAPER
- Dynamic discrete-routing paper run: PASS ON PAPER
- Field-aware stale propagation: PASS ON PAPER
- 10-video transcript/text corpus: PASS 10/10
- Reference direct frame/timeline empirical analysis: **PARTIAL / NON-BLOCKING**
- AniJam workbench: W0 optional supervised-audition candidate / non-blocking
- `DESIGN_COMPLETION_GATE`: **PASS**
- Project state: **DESIGN_COMPLETE / CODE_LOCKED**
- Implementation: **NOT STARTED / NOT AUTHORIZED**

설계 완료 후에도 구현 승인 전 허용되는 작업은 **conditional empirical no-code refinement**뿐이다:
- 직접 관찰 가능한 frame/timeline benchmark
- 실제 publish asset용 source/rights 조사
- materially changed current official tool/platform capability/policy 검증
- supervised UI/workbench audition without integration code
- 실제 새 evidence가 현재 계약을 깨는 경우의 최소 PATCH

새 근거 없이 architecture를 더 늘리지 않는다.
추가 paper pilot도 단순히 활동을 이어가기 위해 만들지 않는다.

**사용자가 미래에 명시적으로 구현을 승인하기 전에는 Implementation Readiness Review조차 구현 코드 작성으로 넘어가지 않는다.**

미래에 명시적 구현 승인이 생기면 다음 순서다:
> **Implementation Readiness Review → runtime pre-mortem → 4 minimal implementation scopes → fixed tool auditions/technology choices → Minimal Supervised Prototype plan → code**

## 10. Visual Production Agent Hierarchy

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

Non-negotiable boundaries:
- Project Orchestrator: state/gate/budget/escalation, shot 미학 micromanage 금지.
- Video Director: shot routing/camera/transition/visual pacing.
- Blender Specialist: topology/axis/cutaway/explode/registered camera 등 spatial truth.
- Generative Cinematic Video: people/atmosphere/historical reconstruction/cinematic bridge. Exact deterministic camera/engineering topology 대체 아님.
- AniJam/other workbench: approved Visual Work Order의 candidate execution만. 자동 scene breakdown은 `NON-CANON` unless upstream-promoted.
- 2D: diagram/map/elevation/causal/state/routing explanation의 first-class capability.
- Visual QA: creator와 논리적으로 분리, reject 권한.
- specialist/workbench가 hard lock/source certainty/reconstruction boundary를 임의 변경 금지.
- 동일 실패 입력 blind retry 금지.
- AniJam/Higgsfield/Veo/특정 SaaS는 core mandatory dependency가 아님.

Relevant contracts:
- `docs/11-design-closure/CAMERA_TRANSITION_GRAMMAR_V1.md`
- `docs/11-design-closure/GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md`

## 11. Full Studio Orchestration

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

Rules:
- Music은 Audio & Post의 specialist responsibility, 별도 top-level orchestra 아님.
- Post Director가 final timeline/picture relationship owner.
- Narration/TTS는 Voice Bible/pronunciation rules 준수.
- Music은 Audio Beat Map/timeline contract를 따르고 narration을 이기지 않음.
- SFX는 S0–S3 truth class를 구분.
- silence는 valid audio state.
- script/claim/spatial 변경은 field-aware downstream stale propagation.
- unresolved rights는 publish blocker.
- title/thumbnail은 Evidence Pack보다 강한 claim 금지.
- realistic synthetic historical reconstruction은 disclosure/reconstruction review를 거침.
- analytics가 trust/accuracy constitution을 override하지 않음.
- Claim Verifier/final Fact-Rights verdict는 creator와 독립.
- critical FAIL은 평균 점수로 상쇄하지 않음.
- mass-produced / interchangeable episode 패턴은 Release/Quality failure 후보.
- music-only/thumbnail-only/Blender-only/AniJam-only/prompt-only orchestra를 기본 추가하지 않음.

Closure audio contract:
- `docs/11-design-closure/AUDIO_TIMELINE_CONTRACT_V1.md`

## 12. Seven Core Artifacts — Locked for Pre-Code Freeze

1. Episode Brief
2. Evidence Pack
3. Story Pack
4. Visual Plan
5. Spatial / Asset Bible
6. Production Pack
7. Review & Run Ledger

Field semantics / dependency matrix:
- `docs/11-design-closure/CORE_ARTIFACT_CONTRACTS_V1.md`

Additive contracts:
- `docs/11-design-closure/DYNAMIC_SYSTEM_CONTRACT_ADDENDUM_V1.md`
- `docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`
- `docs/11-design-closure/GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md`
- `docs/11-design-closure/DESIGN_COMPLETION_GATE_V1.md`

Pilot proof:
- `docs/11-design-closure/pilot-venice/`
- `docs/09-validation/AIRPORT_BAGGAGE_DYNAMIC_ROUTING_PAPER_TEST.md`

Do not add an eighth default core artifact unless a real episode proves one of these cannot carry its responsibility without context/authority/version failure.

## 13. Final Coding Lock

Current authoritative state:

> **DESIGN_COMPLETE / CODE_LOCKED**

Do not create:
- application/runtime code
- Python/TypeScript project scaffold
- LangGraph/agent framework setup
- DB/vector DB implementation
- Blender automation scripts
- AniJam/Veo/Google/provider API integration
- TTS/music integration
- automated publishing
- UI/dashboard/deployment code

until the user later gives an explicit implementation authorization.

**No further architecture expansion is justified without new evidence. No coding is justified without future explicit authorization.**

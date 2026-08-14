# Harness Design Policy

## Purpose

Civilization X-Ray의 하네스는 AI 도구들을 순서대로 호출하는 스크립트가 아니다.

하네스의 목적은 **콘텐츠 아이디어가 조사 → 대본 → 시각 설계 → 제작 → 검수로 이동하는 동안 사실성, 구조 일관성, 의도, 상태, 비용, 실패 이력을 잃지 않게 만드는 운영 시스템**이다.

## Hard Rule

> **Harness follows discovery. Discovery does not follow harness.**

브레인스토밍, 레퍼런스 역설계, 맹점 훑기, pre-mortem, 성공조건이 충분히 정리되기 전에 특정 에이전트 수나 topology를 확정하지 않는다.

## What a Harness Must Contain

### 1. Orchestration
- 누가 현재 phase를 결정하는가?
- 다음 단계로 넘어갈 조건은 무엇인가?
- reject되면 어디로 돌아가는가?
- 병렬화 가능한 작업과 순차 작업은 무엇인가?

### 2. Responsibility Boundaries
각 capability/agent는 한 문장으로 책임이 정의돼야 한다.

금지 예:
- “Research Agent: 조사한다”
- “Quality Agent: 품질을 높인다”

요구 예:
- 입력 artifact, 허용 도구, 산출 artifact, 검증 책임, 하지 않는 일을 명시한다.

### 3. Artifact Contracts
후속 단계가 자연어 대화 기억에 의존하지 않도록 artifact contract를 정의한다.

후보 artifact:
- Topic Brief
- Research Dossier
- Claim Ledger
- Source Pack
- Script Beat Map
- Narration Script
- Script ↔ Visual Map
- Hero Object Bible
- Shot Spec
- Continuity Sheet
- Generation Manifest
- Review Report
- Episode Run Ledger

실제 artifact set은 Discovery 후 확정한다.

### 4. State Model
최소 분리:
- Project state: 프로젝트 헌법/정책
- Channel state: 브랜드 DNA/시각언어/톤
- Episode state: 이번 편의 조사/대본/컷
- Asset state: Hero Object/이미지/영상/오디오 버전
- Run state: 현재 실행 단계/재시도/비용/오류
- Memory state: 장기 학습/실패/선호

### 5. Evidence Lineage
모든 주요 fact claim은 가능한 한 다음 연결을 유지한다.

`claim → source → interpretation → script sentence → visual representation`

시각 재구성은 다음을 구분한다.
- documented fact
- engineering inference
- historical reconstruction
- illustrative simplification

### 6. Quality Gates
하나의 마지막 QA로 몰지 않는다.

후보 gate:
- Topic viability
- Research sufficiency
- Claim verification
- Script structure
- Script ↔ visual alignment
- Hero Object continuity
- Shot feasibility
- Visual consistency
- Final factual review
- Final editorial review

각 gate는 PASS / REVISE / REJECT / ESCALATE 중 하나를 반환할 수 있어야 한다.

### 7. Retry / Recovery
Retry는 동일 prompt 재호출이 아니다.

각 실패 유형에:
- retryable?
- 무엇을 바꿔 재시도하는가?
- 최대 횟수
- 비용 상한
- fallback model/tool
- 사람에게 escalate할 조건
- 이전 단계로 rollback할 조건

을 정의한다.

### 8. Human-in-the-Loop
사람 승인 위치는 비용 대비 오류 영향으로 정한다.

후보 high-value checkpoint:
- topic lock
- research/claim lock
- script lock
- visual bible lock
- expensive generation batch 전
- final publish

승인 지점이 많을수록 안전하지만 throughput이 떨어진다. 실제 위치는 Phase 0에서 결정한다.

### 9. Memory
메모리는 “모든 대화 저장”이 아니다.

필요 memory class 후보:
- Stable rules
- Channel DNA
- Accepted decisions
- Rejected decisions + reason
- Prompt lessons
- Model/tool behavior observations
- Visual continuity conventions
- Failure patterns
- Episode learnings

각 memory에는 가능하면:
- source
- confidence
- created_at
- superseded_by
- applicable scope

를 둔다.

### 10. Observability
“왜 이 결과가 나왔는가?”에 답할 수 있어야 한다.

Run ledger 후보:
- episode id
- stage
- input artifact version
- prompt version
- model/tool
- parameters
- output artifact version
- reviewer result
- retries
- cost estimate
- elapsed time
- failure reason
- decision note

### 11. Vendor Independence
특정 생성 모델 이름을 도메인 로직에 박지 않는다.

하네스는 기능 capability 기준으로 생각한다.
예:
- research/search
- transcription
- frame extraction
- image generation
- image editing
- video generation
- TTS
- compositing/render

모델 선정은 capability registry / adapter 수준의 후속 구현 문제다.

### 12. Budget Controls
비용은 마지막 정산이 아니라 계획 입력이다.

필요 정책 후보:
- episode budget ceiling
- stage budget ceiling
- retry budget
- premium-generation eligibility
- low-cost preview → approve → high-quality render

## Harness Design Sequence

Harness-readiness 통과 후 아래 순서로 설계한다.

1. Episode lifecycle map
2. Artifact map
3. Responsibility map
4. State boundaries
5. Quality/rejection gates
6. Human checkpoints
7. Failure/recovery paths
8. Memory lifecycle
9. Observability/run ledger
10. Cost controls
11. Tool capability boundaries
12. **그 다음에만 agent topology**

즉 “몇 개 에이전트?”는 12번째 질문이다.

## Required 4 Harness Alternatives

최종 topology를 선택하기 전 최소 4안을 비교한다.

초기 비교용 archetype:

### A. Director-Centric
강한 총괄 Director가 각 specialist를 호출하고 모든 상태 전이를 결정.

검토 포인트:
- 통제가 쉽지만 Director context가 비대해지는가?

### B. Stage-Gated Pipeline
Research → Story → Visual Design → Production → QA처럼 stage와 gate 중심.

검토 포인트:
- 재현성이 높지만 iteration이 경직되는가?

### C. Shared Blackboard
공유 episode state/ledger에 specialist들이 artifact를 추가하고 gate가 상태를 전환.

검토 포인트:
- 협업/추적은 좋지만 shared state 오염과 복잡성이 커지는가?

### D. Hierarchical Pods
Director 아래 Research Pod / Story Pod / Visual Pod / Production Pod처럼 내부 specialist와 reviewer를 묶음.

검토 포인트:
- 확장성은 좋지만 초기 프로젝트에 과설계인가?

**주의:** 위 4개는 비교 시작점이지 결론이 아니다. 실제 workflow 분석 결과 더 나은 4안으로 교체할 수 있다.

## Harness Evaluation Matrix

각 안을 최소 다음으로 비교한다.
- Correctness / factual safety
- Script ↔ visual fidelity
- Continuity preservation
- Auditability
- Failure isolation
- Ease of iteration
- Human burden
- Token/context efficiency
- Monetary cost
- Vendor portability
- Operational complexity
- Scale to multiple languages/channels

## Harness Anti-Patterns

- agent count fetish: 에이전트 수 자체를 아키텍처라고 부르기
- fake review: 같은 정보와 같은 기준을 가진 agent가 서로 검증한다고 주장
- context soup: 모든 agent에게 모든 문서를 주기
- invisible handoff: output schema 없이 자연어 대화만 넘기기
- infinite retry: reject 이유 수정 없이 재생성 반복
- last-mile QA: 오류를 끝에서만 발견하기
- vendor-shaped architecture: 특정 SaaS UI/API 구조가 프로젝트 workflow를 결정
- memory landfill: 버전/신뢰도/범위 없는 모든 기록 저장
- premature automation: 사람이 이해하지 못한 과정을 자동화

## Harness Completion Criteria

하네스 설계 “완료”는 diagram 하나가 아니다.

다음이 있어야 한다.
- lifecycle
- roles/responsibilities
- artifact contracts
- state model
- gates
- handoffs
- retry/recovery
- memory policy
- human approvals
- cost policy
- observability
- 4 alternatives comparison
- chosen design rationale
- rejected alternatives rationale
- open risks
- user approval

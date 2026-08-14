# Harness Architecture

Status: **Selected design for Civilization X-Ray**

## Executive Decision

4개 후보를 비교한 결과, Civilization X-Ray는 다음 구조를 채택한다.

> **Stage-Gated Artifact Blackboard + Thin Director**

핵심:
- workflow는 명확한 stage/gate로 진행한다.
- 모든 중요한 상태를 Director의 대화 컨텍스트가 아니라 versioned artifact registry에 둔다.
- Director는 “모든 것을 아는 슈퍼 에이전트”가 아니라 상태 전이, gate, 예산, escalation을 관리한다.
- specialist는 필요한 artifact만 읽고 명확한 contract를 통해 결과를 쓴다.
- agent 수는 고정하지 않는다. 아래의 logical capability를 실행환경에 따라 합치거나 나눌 수 있다.

---

# 1. Four Harness Alternatives

## H-A. Director-Centric

구조:
`User → Director → Specialists → Director → ...`

### Strengths
- 구현/이해가 단순
- 빠른 iteration
- 한 곳에서 의사결정

### Weaknesses
- 긴 episode에서 Director context 비대화
- source/shot/state가 대화 요약 과정에서 손실
- Director가 single point of failure
- 모든 specialist가 Director의 해석에 종속

### Fit
초기 작은 PoC에는 좋으나 8–15분 정교한 롱폼과 multi-artifact provenance에는 약함.

Decision: **Reject as primary architecture.** Thin Director 역할만 유지.

---

## H-B. Stage-Gated Pipeline

구조:
`Topic → Research → Story → Visual → Previs → Production → QA`

각 stage 사이에 gate.

### Strengths
- 제작 순서 명확
- 고비용 작업 전 오류 차단
- 운영/교육 쉬움
- stage별 cost 추적 쉬움

### Weaknesses
- 자연스러운 backtracking이 어렵게 설계될 수 있음
- pipeline 파일만 넘기면 context lineage가 약해질 수 있음
- 병렬 작업 활용 제한 가능

Decision: **Strong base, but insufficient alone.**

---

## H-C. Shared Blackboard

구조:
모든 specialist가 중앙 Episode Blackboard의 artifact/state를 읽고 필요한 결과를 쓴다.

### Strengths
- provenance와 현재 상태 추적 강함
- 여러 reviewer가 동일 source of truth 사용
- 병렬 분석 가능
- rollback/versioning 유리

### Weaknesses
- 모든 것이 shared state가 되면 context soup
- 상태 스키마/권한 설계 필요
- stage discipline 없으면 에이전트가 서로 덮어쓸 위험

Decision: **Adopt artifact/state concept, add strict stage gates.**

---

## H-D. Hierarchical Specialist Pods

구조:
Director 아래 Research / Story / Visual / Production Pod가 각자 내부 specialist와 reviewer 운영.

### Strengths
- 큰 조직/다채널 확장에 유리
- domain isolation 좋음
- 병렬 throughput 높음

### Weaknesses
- 초기에는 과설계
- 같은 정보를 여러 pod가 재요약할 수 있음
- 운영 overhead 큼

Decision: **Future scale option, not Phase 1 default.**

---

# 2. Comparison Matrix

5 = strongest.

| Criterion | H-A Director | H-B Pipeline | H-C Blackboard | H-D Pods |
|---|---:|---:|---:|---:|
| Auditability | 2 | 4 | 5 | 4 |
| Factual lineage | 2 | 4 | 5 | 4 |
| Script↔Visual continuity | 3 | 4 | 5 | 5 |
| Failure isolation | 2 | 4 | 4 | 5 |
| Backtracking | 3 | 3 | 5 | 4 |
| Context efficiency | 2 | 4 | 4 | 4 |
| Initial simplicity | 5 | 4 | 2 | 1 |
| Cost control | 3 | 5 | 4 | 4 |
| Multi-channel scale | 2 | 3 | 4 | 5 |
| Risk of overengineering | 5 low-risk | 4 | 2 | 1 |

Selected hybrid:
**H-B lifecycle + H-C artifact/state + H-A thin orchestration.**

H-D는 scale trigger가 생길 때 도입한다.

---

# 3. Selected Architecture — Stage-Gated Artifact Blackboard

```text
                   ┌─────────────────────────┐
                   │      Thin Director      │
                   │ phase / budget / gate   │
                   │ retry / escalation      │
                   └────────────┬────────────┘
                                │
                  reads state / commands work
                                │
             ┌──────────────────▼──────────────────┐
             │      Episode Artifact Blackboard    │
             │ versions + lineage + status + locks │
             └──────────────────┬──────────────────┘
                                │
      ┌──────────────┬──────────┼───────────┬──────────────┐
      ▼              ▼          ▼           ▼              ▼
  Research        Story      Visual       Produce         QA
 capabilities   capabilities capabilities capabilities capabilities
      │              │          │           │              │
      └──────── artifacts / findings / verdicts ───────────┘
                                │
                         Gate transitions
```

Director는 source dossier 전체, 모든 이미지 프롬프트, 모든 transcript를 항상 context에 보관하지 않는다.
필요한 artifact ID와 gate 상태만 중심적으로 관리한다.

---

# 4. Logical Capability Map

**Logical capability ≠ 반드시 하나의 agent.**
모델/실행환경/비용에 따라 한 agent가 복수 capability를 맡거나 하나의 capability를 병렬 agent로 나눌 수 있다.

## C0. Director / Orchestrator

Owns:
- episode phase
- requested work
- gate transition
- budget
- retry/escalation
- human approval state

Does NOT own:
- factual truth 판단 자체
- script 직접 작성의 최종 authority
- visual asset 세부 생성

## C1. Topic Strategist

Input:
- topic candidates
- channel DNA
- recent topic history

Output:
- Topic Brief
- topic score
- central question candidates

## C2. Research Synthesizer

Input:
- Topic Brief
- source policy

Output:
- Research Dossier
- Claim Ledger draft
- source conflicts
- unknowns

## C3. Claim Verifier

Input:
- raw/primary sources
- Claim Ledger

Output:
- verified / disputed / unsupported verdicts
- provenance corrections

Independence rule:
Research summary만 받아 검증하지 않고 가능한 경우 원 source에 접근.

## C4. Narrative Architect

Input:
- locked claims
- Topic Brief
- episode grammar

Output:
- central question
- Beat Map
- hook/payoff design
- narration draft

## C5. Script–Visual Architect

Input:
- narration
- claims
- visual grammar

Output:
- Script ↔ Visual Map
- visual objective per unit
- reconstruction level
- geometry decision flags

## C6. Asset / Spatial Architect

Input:
- Script ↔ Visual Map
- factual diagrams/references

Output:
- Hero Object Bible
- hard/soft locks
- spatial axes
- asset reuse plan

## C7. Shot Architect

Input:
- visual map
- Hero Object Bible

Output:
- Shot Specs
- camera grammar
- transition map
- low/high risk tags
- fallback visuals

## C8. Previs Evaluator

Input:
- storyboard / proxy / animatic
- script

Output:
- pacing findings
- orientation failures
- missing visual proof
- revised shot requests

## C9. Production Executor

Capabilities may include:
- image generation
- image edit
- geometry/render
- video generation
- TTS
- overlay/composite

Executor는 editorial truth를 결정하지 않는다.
승인된 spec을 제작한다.

## C10. Continuity Reviewer

Checks:
- Hero Object hard locks
- orientation
- component count/position
- cutaway/reassembly
- temporal/era continuity

## C11. Fact / Provenance Reviewer

Checks final script + visuals against claims/source lineage.

## C12. Editorial Reviewer

Checks:
- hook/payoff
- clarity
- repetition
- pacing
- cognitive load

## C13. Rights / Reconstruction Reviewer

Checks:
- reference copying risk
- asset provenance
- reconstruction labeling
- visual certainty vs evidence certainty

### Phase 1 simplification
초기 구현 시 C10–C13을 하나의 실행 process로 묶을 수 있으나 **rubric과 verdict는 분리**해야 한다.

---

# 5. Artifact Blackboard

Blackboard는 거대한 prompt가 아니라 **artifact registry**다.

각 artifact는 최소 개념적으로:
- id
- type
- episode
- version
- status
- created_by capability
- source artifact ids
- created_at
- confidence if relevant
- gate verdict if relevant
- superseded_by

를 가진다.

## Core Artifact Types

### A01 Topic Brief
- central curiosity
- target audience
- scope
- X-Ray value
- initial risks

### A02 Research Dossier
- source-indexed findings
- competing explanations
- terminology
- historical/technical context

### A03 Claim Ledger
각 claim:
- claim text
- source ids
- evidence level
- status
- uncertainty
- visual implications

### A04 Beat Map
- episode grammar
- beats
- question/payoff
- information order

### A05 Narration Script
- narration units linked to claim ids

### A06 Script ↔ Visual Map
- narration unit ↔ visual objective/action

### A07 Hero Object Bible
- canonical spatial definition
- locks
- uncertainty/reconstruction zones

### A08 Shot Spec Pack
- shot goals
- camera
- state transitions
- asset dependencies
- fallback

### A09 Previs Pack
- storyboard/animatic proxies
- review annotations

### A10 Generation Manifest
- selected model/tool capability
- prompt version
- input references
- output versions

### A11 QA Reports
- gate-specific verdicts

### A12 Episode Run Ledger
- state changes
- retries
- costs
- deviations
- human approvals

---

# 6. Episode State Machine

```text
IDEA
 ↓
TOPIC_CANDIDATE
 ↓ Topic Gate
RESEARCHING
 ↓ Research Gate
CLAIMS_LOCKED
 ↓ Story Gate
SCRIPT_DRAFTED
 ↓ Script Gate
VISUAL_MAPPED
 ↓ Visual Map Gate
ASSET_BIBLE_LOCKED
 ↓ Continuity Readiness Gate
PREVIS
 ↓ Previs Gate
PRODUCTION_APPROVED
 ↓
PRODUCING
 ↓
ASSEMBLED
 ↓ QA Gates
FINAL_REVIEW
 ↓ Human Publish Approval
PUBLISHED
 ↓
LEARNING_CAPTURED
```

Possible side states:
- REVISE
- REJECTED
- ESCALATED
- PAUSED_BUDGET
- BLOCKED_SOURCE

---

# 7. Gate Ownership

## Topic Gate
Reviewer must not be the only creator of the Topic Brief.

## Research Gate
Claim Verifier has reject authority.

## Story Gate
Checks central question / structure, not prose beauty only.

## Visual Map Gate
Checks whether each major explanation has explanatory visual proof.

## Continuity Readiness Gate
Asset/Spatial design cannot proceed with unresolved hard geometry contradiction.

## Previs Gate
High-cost production prohibited until pass.

## Final Gates
Fact, Continuity, Editorial, Rights verdicts are separate.

---

# 8. Retry / Rollback Policy

## Local Retry
Use when:
- generation artifact
- minor style miss
- recoverable camera behavior

Must change:
- prompt/spec/model/seed/reference or another causal input.

동일 입력 반복 호출만으로 retry quota를 소비하지 않는다.

## Upstream Revision
Use when:
- visual objective impossible
- script asks for contradictory geometry
- evidence does not support visual

Roll back to:
- Shot Spec
- Script ↔ Visual Map
- Script
- Research

## Escalation
Use when:
- source conflict unresolved
- two plausible reconstructions
- budget ceiling conflict
- no tool meets continuity bar
- rights/provenance uncertainty

## Retry Ceiling
기본 개념:
- local retry count + stage cost ceiling을 함께 둔다.
- 정확한 숫자는 파일럿에서 측정 후 설정.

---

# 9. Context Packaging

모든 agent에게 전체 project를 주지 않는다.

## Context Packet
각 capability 실행 시:
1. task goal
2. applicable project rules
3. required input artifact excerpts/IDs
4. explicit constraints
5. output contract
6. success criteria
7. stop/escalation conditions

을 제공한다.

### Example
Shot Architect에게 전체 Research Dossier를 주는 대신:
- linked claims
- Script ↔ Visual units
- Hero Object locks
- relevant source figures
- camera rules

만 전달.

---

# 10. Memory Architecture

## M0 Constitution Memory
거의 변하지 않는 프로젝트 규칙.

Examples:
- design-first
- source lineage
- no fake precision

## M1 Channel DNA
에피소드 간 재사용.

Examples:
- script grammar
- visual language
- hook patterns
- pacing lessons

## M2 Episode Memory
해당 episode만.

Examples:
- claims
- asset state
- shot decisions

Publication/closure 후 archive.

## M3 Tool/Model Memory
시간에 따라 변함.

Examples:
- 특정 capability의 강점/실패 패턴
- prompt lessons
- continuity observations

반드시 version/date를 갖는다.

## M4 Failure Memory
- failure signature
- cause
- failed attempts
- successful recovery
- applicable conditions

## Memory Rule
낡은 memory는 삭제만이 아니라 superseded 상태로 추적 가능해야 한다.

---

# 11. Human Gates

초기 시즌:

H1 Topic Lock
H2 Claims Lock
H3 Script Lock
H4 Visual/Asset Lock
H5 Previs / expensive production approval
H6 Final Publish

각 human approval은 Run Ledger에 artifact versions와 함께 기록한다.

---

# 12. Budget Harness

Director는 각 stage에:
- estimated cost
- spent cost
- retry spend
- remaining episode budget

상태를 가져야 한다.

고비용 asset을 만들기 전에:
- preview exists?
- visual objective passed?
- reusable asset?
- cheaper fallback?

를 검사.

---

# 13. Observability

최소 질문에 답할 수 있어야 한다.
- 왜 이 shot이 이 모습인가?
- 어떤 claim을 설명하는가?
- 어떤 source가 근거인가?
- 어떤 model/tool/prompt version을 썼는가?
- 몇 번 실패했는가?
- 왜 현재 안을 선택했는가?
- 어느 gate가 승인했는가?

답할 수 없으면 blackboard/ledger가 불충분하다.

---

# 14. Model / Tool Registry Boundary

하네스는 제품명이 아니라 capability를 요청한다.

예:
- `VIDEO_GENERATION: object-consistency-high`
- `IMAGE_GENERATION: reference-conditioned`
- `TRANSCRIPTION: timestamped`
- `GEOMETRY_RENDER: deterministic-camera`

Tool Registry가 현재 사용 가능한 vendor/model과 연결한다.

따라서 미래 모델 변경이 episode workflow를 다시 설계하게 해서는 안 된다.

---

# 15. Scale Triggers for Hierarchical Pods

다음 중 2개 이상이 지속되면 H-D 구조로 확장을 검토한다.
- 동시에 3개 이상 episode production
- 다국어 3개 이상
- 주 3편 이상 롱폼 목표
- Research/Visual queue가 지속 병목
- specialist별 별도 운영자가 생김

그 전에는 pod architecture를 도입하지 않는다.

---

# 16. Harness Success Criteria

하네스는 다음을 만족해야 한다.

1. 오류가 비싼 단계 전에 발견됨
2. source→claim→script→visual lineage 유지
3. Hero Object continuity 유지
4. agent context 크기 통제
5. 실패 시 정확한 upstream으로 rollback
6. 모델 교체 가능
7. human approval 지점 명확
8. 비용/재시도 추적 가능
9. 과거 failure lesson 재사용
10. 어떤 결정이 왜 내려졌는지 재현 가능

---

# Final Harness Decision

**Selected:** Stage-Gated Artifact Blackboard + Thin Director.

선택 이유:
- 이 프로젝트의 가장 큰 위험은 “생성 실패”보다 **정보/공간/의도/근거가 단계 사이에서 사라지는 것**이다.
- stage gate는 비싼 작업 전에 문제를 막는다.
- artifact blackboard는 롱폼의 많은 claim/shot/asset을 Director context 바깥에 안정적으로 보존한다.
- thin Director는 중앙통제의 장점은 유지하면서 context 비대화와 single-agent truth 문제를 줄인다.

이 구조는 디자인 결론이며 구현 기술/프레임워크 선택은 아직 하지 않는다.

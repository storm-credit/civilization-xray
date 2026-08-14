# Production System

## Production Philosophy

Civilization X-Ray는 “프롬프트 한 번 → 영상 완성”을 목표로 하지 않는다.

목표는:

> **비용이 싼 단계에서 오류를 최대한 빨리 발견하고, 고비용 generation은 검증된 설계만 통과시키는 stage-gated production.**

---

# Four Production Philosophies

## P-A. Fully Generative
Topic → Script → image/video generation → edit.

장점:
- 빠른 시작
- 구현 단순

단점:
- continuity와 factual visual integrity 취약
- 재생성 비용 급증

Decision: Reject as default.

## P-B. Asset-First 3D
모든 주요 구조를 먼저 모델링하고 이후 촬영/합성.

장점:
- 구조 통제력 최고
- 재사용성 높음

단점:
- 초기 제작비/시간 과다
- 모든 소재에 불필요한 모델링 발생

Decision: Reject as universal default; use selectively.

## P-C. Hybrid Stage-Gated
Research → Script/Visual Map → Hero Asset decision → cheap previs → approval → high-quality generation/render → final QA.

장점:
- 비용과 품질 균형
- 구조 설명 컷만 geometry-backed 가능
- 실패를 앞 단계에서 잡기 쉬움

Decision: **Selected.**

## P-D. Human Studio + AI Assist
사람이 모든 editorial/shot decision을 하고 AI는 보조.

장점:
- 최고 통제력

단점:
- 자동화 자산 축적 느림
- throughput 낮음

Decision: Initial fallback for hard episodes, not default target.

---

# Episode Lifecycle

## Stage 0 — Topic Intake
Input:
- topic idea
- why now / why interesting

Output:
- Topic Brief

Gate:
- Topic Viability

Reject if:
- X-Ray value weak
- evidence weak
- copy risk high

## Stage 1 — Research

Output:
- Research Dossier
- Claim Ledger
- Source Pack
- uncertainty map

Gate:
- Research Sufficiency
- Claim Verification

No script lock before major claims are traceable.

## Stage 2 — Story Design

Output:
- central question
- episode grammar
- beat map
- hook/payoff
- narration draft

Gate:
- Script Structure
- Accuracy consistency

## Stage 3 — Script ↔ Visual Mapping

Output:
- narration units
- visual objectives
- visual actions
- spatial/camera plan
- evidence/reconstruction levels

Gate:
- Script ↔ Visual Alignment

## Stage 4 — Visual Bible

Decision:
- AI-only scene?
- geometry-backed?
- actual/reference footage?
- diagram?

Output:
- Hero Object Bible
- style/era references
- hard/soft continuity locks
- visual truth rules

Gate:
- Continuity readiness

## Stage 5 — Previsualization

저비용으로 전체 episode를 먼저 검증한다.

가능한 형태:
- storyboard stills
- low-res generations
- proxy geometry
- animatic
- scratch narration

검증:
- 공간 이해
- 정보 pacing
- camera continuity
- 필요한 asset 누락

**High-cost generation 전에 반드시 존재.**

## Stage 6 — Production Batch

승인된 shot spec만 고품질 제작.

batch는 위험도 기준으로 나눈다.
- deterministic/cheap
- generative medium risk
- expensive/high-risk

고위험 batch는 먼저 sample 1–2개를 검증하고 확대한다.

## Stage 7 — Assembly

- narration
- visual shots
- overlays
- labels
- music/SFX
- citations/description source notes

을 timeline으로 통합.

## Stage 8 — QA

독립적으로:
- factual QA
- visual continuity QA
- script/visual sync QA
- editorial/pacing QA
- rights/provenance QA

## Stage 9 — Publish Package

Output:
- final master
- title candidates
- thumbnail candidates
- description/source notes
- chapters if appropriate
- derivatives/short clips candidates

## Stage 10 — Post-Publish Learning

수집:
- audience metrics
- comments/trust issues
- expensive/problem shots
- prompt/model lessons
- editorial lessons

episode memory와 channel memory를 구분해 반영한다.

---

# Cheap-to-Expensive Funnel

비용 순서를 역전하지 않는다.

1. Text research
2. Claims
3. Beat map
4. Script/visual map
5. rough still/storyboard
6. proxy animatic
7. selected final assets
8. expensive video/render
9. final compositing

실패가 8번에서 처음 발견되면 시스템 설계 실패로 간주한다.

---

# Human Approval Strategy

## Initial Season
필수 human checkpoints:
- Topic Lock
- Research/Claim Lock
- Script Lock
- Visual Bible Lock
- Previs Lock
- Final Publish

## Graduation Rule
특정 gate가 반복적으로 사람 수정 없이 통과하면 자동화 후보가 된다.

예:
- 10개 episode에서 claim formatting이 안정됨 → format approval 자동화 가능

그러나 다음은 자동 승인에 더 높은 증거 필요:
- 역사적 reconstruction
- sensitive factual claims
- expensive render batch
- final publish

---

# Production Budget Design

아직 실제 가격/벤더를 고정하지 않는다.

Episode Budget은 다음 단위로 추적할 수 있어야 한다.
- research/search
- transcription/reference analysis
- image generation
- video generation
- 3D/render
- TTS
- post-processing
- human review time

## Budget Gate

예상 비용이 ceiling을 넘으면 순서:
1. visual objective가 꼭 필요한가?
2. cheaper explanatory technique가 있는가?
3. shot reuse 가능한가?
4. lower-res preview로 검증했는가?
5. 그래도 필요하면 Director escalation.

---

# Multi-Language Future Boundary

초기에는 한국어 script를 최적화한다.

하지만 향후 다국어를 위해 language-neutral artifact를 분리한다.

예:
- claims
- visual map
- shot specs
- Hero Object Bible

는 언어에 덜 종속.

다국어 단계에서 새로 생성:
- narration adaptation
- on-screen labels
- cultural analogy
- title/thumbnail copy

단순 직역을 기본값으로 하지 않는다.

---

# Stop Conditions

episode를 억지로 끝까지 만들지 않는다.

STOP/RETHINK 조건:
- 핵심 claim을 신뢰할 자료로 확인할 수 없음
- Hero Object continuity가 설명 기준을 만족하지 못함
- visual cost가 예상 가치를 크게 초과
- 핵심 질문이 이미 초반에 너무 단순하게 해결돼 롱폼 가치가 없음
- reference와 지나치게 유사해 고유성이 약함
- reconstruction이 사실처럼 오해될 위험을 해결하기 어려움

---

# Production Completion Definition

“영상 파일이 생성됨”이 아니다.

완료에는:
- all major claims traced
- script/visual mapping complete
- continuity checks pass
- reconstruction labels handled
- QA reports pass
- final artifact reproducibility metadata preserved
- post-publish learning slot created

가 포함된다.

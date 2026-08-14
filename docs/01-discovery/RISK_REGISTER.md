# Risk Register — Completed Blind-Spot Sweep

Status: **Phase 0 director review completed**

이 문서는 `BLIND_SPOT_SWEEP.md`의 체크리스트를 실제 설계 결정으로 전환한 결과다.

Scale:
- Severity: Critical / High / Medium / Low
- Likelihood: High / Medium / Low

---

# Top Risks

## R1. AI 3D Continuity Collapse

- Severity: **Critical**
- Likelihood: High if pure generative pipeline
- Failure: 같은 건물/구조물이 컷마다 다른 topology로 변해 설명 자체가 틀림.
- Early signal:
  - column/window/component count drift
  - cutaway 내부가 exterior와 불일치
  - orbit 중 topology 변형
- Prevention:
  - Hero Object Bible
  - hard/soft/free locks
  - geometry decision rule
  - low-cost previs before final generation
- Detection:
  - Continuity Reviewer
  - shot-to-shot hard-lock check
- Recovery:
  - local retry if rendering issue
  - rollback to asset/shot design if topology issue
- Stop condition:
  - 설명에 핵심인 topology를 안정적으로 유지할 방법이 없으면 episode 재설계 또는 중단.
- Harness implication:
  - Asset/Spatial capability와 independent continuity gate 필요.

## R2. Visual Fake Precision

- Severity: **Critical**
- Likelihood: Medium–High for historical content
- Failure: 정확히 알려지지 않은 고대/역사 구조를 photoreal하게 보여줘 사실처럼 오해시킴.
- Early signal:
  - source에 없는 내부 구조가 script/visual map에 등장
  - “아마”인 claim인데 image prompt는 exact specification 요구
- Prevention:
  - R0–R3 reconstruction levels
  - fact/inference/reconstruction/illustration 분리
- Detection:
  - Claim Verifier + Rights/Reconstruction Reviewer
- Recovery:
  - visual stylization / disclaimer / alternative reconstruction / simplified diagram
- Stop condition:
  - 핵심 payoff가 불확실한 재구성에만 의존하면 reject.
- Harness implication:
  - claim→visual lineage가 필수.

## R3. Research Summary Echo Chamber

- Severity: **Critical**
- Likelihood: Medium
- Failure: Research Agent와 Fact Checker가 같은 요약문을 공유해 독립 검증처럼 보이지만 같은 오류를 반복.
- Early signal:
  - reviewer citation이 creator summary와 동일
  - 원 source 확인 기록 없음
- Prevention:
  - Claim Verifier는 원 source/reliable source view 확보
  - reviewer rubric 분리
- Detection:
  - provenance audit
- Recovery:
  - disputed claim을 다시 source-first research
- Stop condition:
  - central claim verification 불가 시 topic 중단.
- Harness implication:
  - reviewer independence를 agent count가 아니라 evidence access로 설계.

## R4. Expensive Late-Stage Failure

- Severity: **Critical**
- Likelihood: High without gates
- Failure: 비싼 final video를 만든 뒤 script/continuity 문제 발견.
- Early signal:
  - storyboard/animatic 없이 premium generation 시작
  - shot objective 미승인
- Prevention:
  - cheap-to-expensive funnel
  - Previs Gate hard requirement
- Detection:
  - Director blocks production state transition
- Recovery:
  - rollback before production batch
- Stop condition:
  - previs PASS 없으면 high-cost generation 금지.
- Harness implication:
  - stage gate와 budget state 필요.

## R5. Channel Identity Dilution

- Severity: High
- Likelihood: Medium
- Failure: 건축/도시/역사를 다루다가 잡학/여행/역사 요약 채널이 됨.
- Early signal:
  - topic brief에 hidden mechanism이 없음
  - 3D 해부 없이도 영상 가치 동일
- Prevention:
  - Civilization X-Ray umbrella
  - Topic Score + X-Ray hard reject
- Detection:
  - Topic Gate
- Recovery:
  - central question 재설계 또는 reject
- Stop condition:
  - “X-Ray로 보여줄 보이지 않는 원리”를 한 문장으로 못 쓰면 탈락.

## R6. Repetition of the Same Visual Trick

- Severity: High
- Likelihood: Medium
- Failure: 모든 영상이 exterior→cutaway→explode→reassembly 패턴으로 보여 피로감.
- Early signal:
  - episode grammar와 무관하게 같은 shot recipe
- Prevention:
  - 4 episode grammars
  - visual action taxonomy는 선택지이지 checklist가 아님
- Detection:
  - cross-episode editorial review
- Recovery:
  - journey/build/failure grammar로 재설계
- Stop condition:
  - 없음; editorial revision.

## R7. Over-Automation Before Understanding

- Severity: High
- Likelihood: High if implementation starts early
- Failure: 잘못 이해한 workflow를 자동화해 복잡한 하네스만 남음.
- Early signal:
  - agent 수/프레임워크가 artifact보다 먼저 결정
  - full-auto 목표가 quality definition보다 앞섬
- Prevention:
  - Design-first rule
  - Harness Readiness Gate
  - Phase 1 supervised workflow
- Detection:
  - architecture review
- Recovery:
  - responsibilities/artifacts로 되돌아가 topology 축소
- Stop condition:
  - 실제 workflow에서 필요성을 설명 못 하는 agent는 추가하지 않음.

## R8. Director Context Bloat

- Severity: High
- Likelihood: High in long-form
- Failure: Director가 source/script/shot 전부 들고 있어 context overflow와 상태 손실 발생.
- Early signal:
  - 매 단계 전체 dossier 재주입
  - decision이 대화 기억에만 존재
- Prevention:
  - Thin Director
  - Artifact Blackboard
  - Context Packet
- Detection:
  - context/token metrics
- Recovery:
  - artifact extraction + targeted context
- Stop condition:
  - 없음; architecture correction.

## R9. Model/Vendor Lock-In

- Severity: High
- Likelihood: Medium
- Failure: 특정 AI video SaaS 기능 변경/가격/API 제한으로 전체 workflow 붕괴.
- Early signal:
  - episode spec에 제품별 명령이 직접 들어감
- Prevention:
  - capability registry boundary
  - product-specific adapter는 구현 후단
- Detection:
  - architecture dependency review
- Recovery:
  - alternative capability provider
- Stop condition:
  - 핵심 workflow가 한 vendor UI에만 가능한 경우 design risk escalation.

## R10. Cost Spiral from Regeneration

- Severity: High
- Likelihood: High for video generation
- Failure: 한 컷 continuity를 맞추기 위해 무제한 재생성.
- Early signal:
  - 같은 prompt 반복
  - retry count와 비용 추적 없음
- Prevention:
  - retry causal change rule
  - stage/episode budget
  - proxy validation
- Detection:
  - Run Ledger
- Recovery:
  - fallback visual, geometry-backed method, shot redesign
- Stop condition:
  - 동일 failure class 2회 이상 → upstream review.

## R11. Script Becomes Encyclopedia

- Severity: High
- Likelihood: Medium
- Failure: 정확하지만 재미없고 공간적으로 따라가기 어려운 정보 나열.
- Early signal:
  - central question 없이 연도/수치 연속
  - narration에 새 개념이 빠르게 누적
- Prevention:
  - question lock
  - beat map
  - one spatial concept per shot
- Detection:
  - Story Gate / Editorial QA
- Recovery:
  - mechanism chain 재구성

## R12. Visuals Become Decorative B-Roll

- Severity: High
- Likelihood: Medium
- Failure: 제작비는 높지만 화면이 narration을 증명하지 않음.
- Early signal:
  - visual objective가 “멋진 도시 장면” 수준
- Prevention:
  - Script ↔ Visual Map
  - visual action taxonomy
- Detection:
  - alignment score
- Recovery:
  - shot 목적부터 재설계

## R13. Copyright / Reference Over-Imitation

- Severity: High
- Likelihood: Medium
- Failure: 레퍼런스의 distinctive 문장/shot sequence/branding을 너무 가깝게 복제.
- Early signal:
  - reference timeline이 그대로 우리 timeline으로 이동
- Prevention:
  - Anti-Copy Rule
  - “learn / do not copy” 분리
  - 여러 reference synthesis
- Detection:
  - Rights Reviewer
- Recovery:
  - question/shot order/visual signature 재설계
- Stop condition:
  - 고유한 재설계가 안 되면 해당 reference-inspired concept 보류.

## R14. Historical Reconstruction Cost Explosion

- Severity: Medium–High
- Likelihood: Medium
- Failure: 시대 의상/도시/군중/건축 정확도를 동시에 맞추다 생산성이 붕괴.
- Prevention:
  - historical scene은 mechanism을 설명하는 데 필요한 만큼만
  - reconstruction level과 screen time 제한
- Recovery:
  - diagram/miniature/stylized reconstruction

## R15. Multi-Language Premature Complexity

- Severity: Medium
- Likelihood: Medium
- Failure: 한국어 한 채널도 검증 전 다국어 구조로 과설계.
- Prevention:
  - language-neutral artifact boundary만 설계
  - 번역 자동화 구현은 성과 후

---

# Pre-Mortem — “3개월 후 실패했다면?”

## Scenario A — 영상은 화려한데 조회 유지가 안 됨

Likely causes:
- hook은 강하지만 question/payoff chain 약함
- 3D 변화가 너무 잦아 이해보다 피로
- 대본이 encyclopedic

Countermeasure:
- first 30s / beat / visual transformation을 별도 평가
- post-publish retention과 quality score correlation

## Scenario B — 한 편 만드는데 너무 오래 걸림

Likely causes:
- 모든 장면 full 3D
- generation retry 폭주
- human approval 과다

Countermeasure:
- Geometry Decision Rule
- cheap previs
- gate graduation
- cost/minute 추적

## Scenario C — AI 티가 나서 정교함이 무너짐

Likely causes:
- Hero Object lock 부족
- image→video만으로 topology 유지 시도

Countermeasure:
- geometry-backed structural shots
- Continuity Reviewer
- AI artifact reject list

## Scenario D — 댓글에서 사실 오류 지적이 반복됨

Likely causes:
- 2차 출처 복제
- source lineage 손실
- visual fake precision

Countermeasure:
- documentary-grade claim ledger
- independent fact review
- reconstruction levels

## Scenario E — 시스템이 너무 복잡해 운영 불가능

Likely causes:
- 에이전트 수를 먼저 고정
- 모든 risk마다 새 agent 추가
- blackboard가 data landfill

Countermeasure:
- logical capability와 physical agent 분리
- YAGNI
- artifact 최소화
- scale trigger 전 hierarchical pods 금지

---

# Residual Risks Accepted in Phase 0

다음은 설계만으로 제거하지 않는다.

1. 실제 AI 모델별 continuity 성능
   - 해결: Phase 1 capability benchmark

2. 실제 제작비/분
   - 해결: 3편 pilot 측정

3. 실제 retention
   - 해결: publish 후 데이터

4. benchmark reference의 정확한 production toolchain
   - 해결할 필요 없음. observable grammar만 학습.

5. 최적 agent 수
   - 해결: 구현/운영에서 측정; design은 logical roles만 고정.

---

# Blind-Spot Completion Judgment

Phase 0 기준으로 **하네스 방향을 선택하기에 충분한 수준의 맹점 훑기는 완료**로 판정한다.

근거:
- Critical/High 위험과 대응이 artifact/gate 설계로 연결됨
- 가장 큰 위험인 continuity, fake precision, late-stage cost, echo-chamber review가 architecture에 반영됨
- unknown 영역은 implementation 전에 측정할 pilot/benchmark로 분리됨

단, 이는 프로젝트 전체 risk review가 끝났다는 뜻이 아니다. 새 모델/새 episode type/새 플랫폼이 추가되면 risk register를 갱신한다.

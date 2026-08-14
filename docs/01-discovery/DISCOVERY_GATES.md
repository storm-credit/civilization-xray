# Discovery Gates

이 문서는 Civilization X-Ray가 아이디어 단계에서 하네스 설계, 구현 계획으로 넘어가기 위해 반드시 통과해야 하는 게이트를 정의한다.

## Gate 0 — Context Complete Enough

통과 조건:
- 프로젝트 목적이 한 문장으로 설명 가능하다.
- 현재 금지사항과 비목표가 문서화돼 있다.
- 참고 대상과 참고 이유가 구분돼 있다.
- 모르는 것을 모른다고 표시한 open questions가 있다.

실패 시:
- 추가 Context Dump
- 사용자에게 필요한 질문을 한 번에 하나씩 진행

## Gate 1 — User Intent Interview

최소 인터뷰 범주:
- 진짜 목적: 조회수 / 수익화 / 작품성 / 기술 실험 / 자동화 자산 중 우선순위
- 주사용자/주 시청자
- 한국어/글로벌 여부
- 롱폼 길이와 발행 목표
- 원하는 사실 정확도 수준
- 원하는 3D 정교함 수준
- 사람 개입 허용량
- 월 예산/렌더 비용 감내 범위
- 성공했다고 판단할 3~5개 지표

통과 조건:
- 중요한 결정에 직접 영향을 주는 질문이 미답 상태가 아니다.
- 답을 못 정한 항목은 가설과 검증방법이 붙어 있다.

## Gate 2 — Reference Reverse Engineering

최소 분석 단위:
- 제목/썸네일 약속
- 첫 30초 hook
- 전체 script beats
- 정보 공개 순서
- 문장별 visual action
- camera grammar
- cut / section rhythm
- diagram / cross-section / exploded view 사용법
- Hero Object continuity
- sound / narration 역할
- 팩트와 재구성의 경계
- 엔딩 payoff

중요 원칙:
- transcript만 보지 않는다.
- frame/scene와 timestamped transcript를 함께 본다.
- “무엇을 말했는가”뿐 아니라 “그 문장을 화면에서 어떻게 증명했는가”를 기록한다.

통과 조건:
- 최소 여러 편에서 반복되는 패턴과 예외 패턴이 구분된다.
- 레퍼런스의 강점을 베끼지 않고 추상화한 design rules가 나온다.

## Gate 3 — Four-Way Brainstorming

중요한 축마다 4안을 한눈에 비교한다.

필수 4안 대상:
1. Content positioning
2. Episode grammar
3. Visual language
4. Production philosophy
5. 이후 Harness architecture

각 안은 다음을 포함한다.
- 핵심 아이디어
- 장점
- 단점
- 예상 실패모드
- 제작 난이도
- 차별성
- 비용/속도 영향
- 어떤 성공조건에 유리한가

통과 조건:
- 추천안뿐 아니라 탈락 이유가 남아 있다.
- 필요하면 hybrid 안을 만들되, 장점만 모은 비현실적 혼합안은 금지한다.

## Gate 4 — Blind-Spot Sweep

`BLIND_SPOT_SWEEP.md`의 모든 범주를 검토한다.

통과 조건:
- Critical / High 위험에 owner 또는 대응 방식이 있다.
- 모르는 위험은 “unknown”으로 남기고 검증 계획을 붙인다.
- 위험을 발견했다고 자동으로 범위를 키우지 않는다. YAGNI 원칙으로 필요한 대응만 한다.

## Gate 5 — Pre-Mortem / Trap Check

질문:
> 3개월 후 이 프로젝트가 실패하거나 영상 품질이 무너졌다고 가정하면 가장 가능성 높은 이유는 무엇인가?

각 위험에:
- Failure mode
- Earliest signal
- Prevention
- Detection
- Recovery
- Stop condition

을 기록한다.

## Gate 6 — Success Criteria & Scorecard

최소 scorecard 축:
- Factual integrity
- Script clarity
- Hook/payoff
- Script ↔ visual alignment
- Spatial/structural continuity
- Visual explanatory value
- Long-form coherence
- Production repeatability
- Cost efficiency
- Human review burden

통과 조건:
- “좋아 보인다”가 아니라 reject/pass 기준이 있다.

## Gate 7 — Harness Readiness

**이 Gate가 핵심이다. Gate 0~6을 통과하기 전 하네스를 확정하지 않는다.**

하네스를 설계할 준비가 됐다는 것은 최소 다음이 드러났다는 뜻이다.

- 실제 workflow의 단계
- 단계별 책임
- 단계 사이에 이동하는 artifact
- 사람이 승인해야 할 지점
- 실패했을 때 되돌아갈 지점
- 기억해야 할 장기 정보
- episode마다 초기화돼야 할 정보
- 품질을 검사할 독립 gate
- 모델에 종속되면 안 되는 경계

Harness-readiness checklist:
- [ ] 대표 episode type 3개 이상
- [ ] reference grammar 정리
- [ ] content positioning 결정 또는 좁혀진 후보
- [ ] visual rules 초안
- [ ] source/evidence policy
- [ ] success scorecard
- [ ] blind spots reviewed
- [ ] pre-mortem reviewed
- [ ] required artifacts identified
- [ ] state handoffs identified
- [ ] human checkpoints identified

하나라도 핵심 항목이 비어 있으면 harness 설계를 보류한다.

## Gate 8 — Harness Architecture Review

Harness 4안을 비교한다.

예시 archetype은 이후 분석을 통해 정하되, 최소 다음 축을 비교한다.
- 중앙집중형 Director
- Pipeline / stage-gated
- Blackboard / shared-state
- Hierarchical / specialist pods

이 예시는 선결정이 아니다. Discovery 결과에 따라 다른 구조가 나올 수 있다.

통과 조건:
- agent 개수가 아니라 책임 경계로 설계됨
- input/output contract가 존재함
- reject/retry/escalation 경로가 존재함
- shared memory와 episode state가 분리됨
- cost/latency/quality trade-off가 설명됨
- 특정 AI vendor가 바뀌어도 핵심 flow가 유지됨

## Gate 9 — Written Design Approval

사용자가 설계 문서를 검토하고 승인해야 한다.

그 전에는 implementation plan과 code로 이동하지 않는다.

## Gate 10 — Implementation Planning

오직 Gate 9 이후에만 수행한다.

- exact scope
- exact files
- verification
- rollback
- minimal implementation

을 포함한다.

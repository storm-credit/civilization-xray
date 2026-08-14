# Harness Readiness Review

Date: 2026-08-14
Status: **PASS — design-level readiness**

이 review는 “구현할 준비”가 아니라 **하네스 구조를 설계할 만큼 도메인/위험/산출물이 드러났는지** 판정한다.

---

# Gate Review

## G0. Context Complete Enough — PASS

Evidence:
- `CLAUDE.md`
- `docs/00-project/PROJECT_CHARTER.md`
- `docs/00-project/REFERENCE_METHODS.md`

확인:
- 프로젝트 목적/비목표/코드 금지선 명시
- 참고 저장소 역할 분리
- 미확정 항목의 처리 규칙 존재

## G1. User Intent — PASS WITH REVERSIBLE ASSUMPTIONS

Evidence:
- `docs/01-discovery/USER_INTERVIEW.md`
- `docs/01-discovery/PHASE0_DECISIONS.md`

사용자가 설계를 질문 대기 없이 자동 진행하도록 지시했으므로, 미답 항목은 가역적 Director decision으로 닫았다.

핵심 결정:
- quality first → supervised automation → scale
- 한국 대중형 롱폼 우선
- “문명의 숨은 구조” umbrella
- geometry-backed hybrid visual truth
- documentary-grade provenance

## G2. Reference Method — PASS FOR ARCHITECTURE, BENCHMARK EXECUTION PENDING

Evidence:
- `docs/01-discovery/REFERENCE_REVERSE_ENGINEERING.md`
- `docs/00-project/REFERENCE_METHODS.md`

현재 설계에서는 reference를 transcript-only로 분석하지 않고 timestamp transcript + frames + script↔visual alignment로 분석하도록 확정했다.

Pending empirical work:
- anchor reference 포함 실제 10-video corpus execution

판정 이유:
- 하네스 책임/산출물을 설계하는 데 필요한 분석 dimension은 충분히 정의됨.
- 그러나 implementation 전에 실제 corpus가 현재 Script/Visual Grammar를 반박하는지 확인해야 한다.

이 pending은 harness topology를 지금 선택하지 못하게 하는 blocker가 아니라 **pre-implementation validation gate**로 남긴다.

## G3. Four-Way Brainstorming — PASS

Evidence:
- Content positioning 4안: `CONTENT_SYSTEM.md`
- Visual direction 4안: `VISUAL_SYSTEM.md`
- Production philosophy 4안: `PRODUCTION_SYSTEM.md`
- Harness topology 4안: `HARNESS_ARCHITECTURE.md`
- Script grammar 4종: `SCRIPT_VISUAL_GRAMMAR.md`

탈락/채택 이유 기록됨.

## G4. Blind-Spot Sweep — PASS

Evidence:
- `BLIND_SPOT_SWEEP.md`
- `RISK_REGISTER.md`

Critical/High risks:
- continuity collapse
- fake precision
- review echo chamber
- late-stage cost failure
- identity dilution
- repetitive visual grammar
- premature automation
- Director context bloat
- vendor lock-in
- retry cost spiral
- encyclopedic script
- decorative visuals
- copying/provenance

각 주요 risk가 architecture decision에 연결됨.

## G5. Pre-Mortem — PASS

Evidence:
- `RISK_REGISTER.md`

3개월 실패 scenario 5종과 예방책이 존재.

## G6. Success Criteria — PASS

Evidence:
- `docs/07-quality/QUALITY_SCORECARD.md`

100-point weighted score + hard fail + stage threshold 정의.

## G7. Harness Readiness — PASS

Checklist:
- [x] 대표 episode type 3개 이상 — 4개 정의
- [x] reference grammar 분석 dimension 정의
- [x] content positioning 결정
- [x] visual rules 정의
- [x] source/evidence policy 정의
- [x] success scorecard 정의
- [x] blind spots reviewed
- [x] pre-mortem reviewed
- [x] required artifacts identified
- [x] state handoffs identified
- [x] human checkpoints identified

## G8. Harness Architecture — PASS

Evidence:
- `HARNESS_DESIGN_POLICY.md`
- `HARNESS_ARCHITECTURE.md`

4 alternatives compared.

Selected:
**Stage-Gated Artifact Blackboard + Thin Director**

---

# Why the Harness Is Now Justified

Discovery에서 드러난 핵심 문제는 다음과 같다.

1. 영상은 long-form이라 context와 상태가 크다.
2. 핵심 claim과 visual이 연결돼야 한다.
3. 구조물 geometry/continuity가 shot 사이에 유지돼야 한다.
4. historical reconstruction은 certainty를 잃으면 안 된다.
5. generation은 비싸므로 오류를 일찍 잡아야 한다.
6. 서로 다른 reviewer는 실제 독립 근거를 봐야 한다.
7. model/vendor는 바뀔 수 있다.

따라서:
- 단일 대화/Director memory는 부족
- 단순 linear file handoff도 provenance/rollback이 약함
- 초기부터 hierarchical pods는 과설계

이라는 결론이 나왔다.

Stage Gates가 3/5번 문제를 해결하고,
Artifact Blackboard가 1/2/4/6번 문제를 해결하며,
Thin Director + capability registry가 7번과 context bloat를 완화한다.

즉 harness는 취향으로 선택한 것이 아니라 discovery risk에서 도출됐다.

---

# Remaining Validation Before Implementation

설계 자체는 완료 가능하지만 구현 시작 전 다음 validation을 권장/요구한다.

## V1. Reference Corpus Validation
실제 benchmark 10편 분석.

목표:
- current script/visual grammar가 관찰 데이터와 맞는지 확인
- 누락된 visual actions/camera patterns 추가

## V2. Three Pilot Episode Paper Walkthroughs
코드를 만들지 않고 3개 주제에 artifact flow를 손으로 적용.

추천:
- Venice foundations
- Roman aqueduct
- undersea tunnel alignment

확인:
- artifact가 과도하게 많지 않은가?
- 필요한 정보가 handoff에서 빠지는가?
- reviewer gate가 너무 늦거나 많은가?

## V3. Capability Benchmark Plan
실제 구현 시에만 수행.

비교 대상은 제품명이 아니라 capability:
- reference-conditioned image
- structural consistency video
- deterministic geometry/camera
- timestamp transcription
- TTS

---

# Final Readiness Judgment

**Harness design can be considered complete at architecture level.**

단:
- logical capability ≠ fixed agent count
- actual model/vendor/framework ≠ selected
- data schema implementation ≠ started
- automation code ≠ started

따라서 사용자의 “브레인스토밍과 맹점 훑기가 충분히 된 뒤 그에 맞는 하네스를 잡는다”는 원칙을 만족하면서도 premature implementation은 피한다.

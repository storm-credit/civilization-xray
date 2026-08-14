# Quality Scorecard

## Purpose

Civilization X-Ray에서 “좋다/정교하다/재밌다”를 감으로만 판단하지 않기 위한 평가 기준이다.

모든 점수는 0–5.
- 0 = unusable / critical failure
- 1 = poor
- 2 = below bar
- 3 = passable
- 4 = strong
- 5 = reference quality

## Hard-Fail Rules

아래는 총점과 무관하게 FAIL 가능.
- 핵심 claim의 출처가 없거나 상충 자료를 무시함
- 역사적 재구성을 확정 사실처럼 표현
- Hero Object의 hard lock이 장면 사이에서 바뀜
- visual이 narration의 핵심 mechanism과 모순
- 타 채널의 distinctive script/shot sequence를 지나치게 가깝게 모방
- 저작권/출처 provenance가 불명확한 핵심 자산

---

# Score Dimensions

## Q1. Factual Integrity — weight 15

5:
- major claim이 신뢰도 높은 source와 trace됨
- 상충 자료/불확실성이 명시됨
- 설명 단순화가 사실을 왜곡하지 않음

3:
- 대부분 추적 가능하나 일부 peripheral claim이 약함

0–2:
- source lineage 부재 또는 사실/추론 혼합

## Q2. Claim Provenance — weight 10

5:
`source → claim → script → visual` 연결이 명확.

## Q3. Central Question & Payoff — weight 10

5:
- 첫 30–45초 안에 질문이 명확
- 결말에서 정확히 회수
- clickbait gap 없음

## Q4. Script Clarity — weight 10

5:
- 전문지식 없이 원리 추적 가능
- 인지 부하 제어
- 한 번에 한 핵심 개념

## Q5. Script ↔ Visual Alignment — weight 15

5:
- 주요 설명 문장마다 화면이 의미를 실제로 설명/증명
- B-roll 의존 낮음

## Q6. Spatial / Structural Continuity — weight 15

5:
- hard locks 유지
- orientation 이해 가능
- cutaway/explode/reassembly 일관

## Q7. Visual Explanatory Value — weight 10

5:
- 3D/시각화가 없으면 이해하기 어려운 것을 실제로 명확하게 만듦

## Q8. Long-form Coherence — weight 5

5:
- 8–15분 전체가 하나의 질문으로 연결
- section 간 repetition/탈선 적음

## Q9. Production Repeatability — weight 5

5:
- input/output artifact와 상태가 명확
- 특정 개인의 머릿속 정보에 의존하지 않음

## Q10. Cost / Human Burden — weight 5

5:
- explanation value 대비 generation/review 비용이 합리적

Total weight = 100.

---

# Recommended Gate Thresholds

## Topic Gate
필수:
- X-Ray value >= 4
- evidence feasibility >= 3
- differentiation >= 3

## Research Gate
- Factual Integrity >= 4
- Claim Provenance >= 4
- Critical uncertainty unresolved = 0

## Script Gate
- Central Question & Payoff >= 4
- Script Clarity >= 4
- factual contradiction = 0

## Visual Map Gate
- Script ↔ Visual Alignment >= 4
- Visual Explanatory Value >= 4

## Previs Gate
- Spatial Continuity >= 4
- Long-form Coherence >= 3
- hard-lock violations = 0

## Final QA
- Weighted total >= 80
- Q1, Q5, Q6 each >= 4
- hard fail = 0

초기 3개 파일럿을 본 뒤 threshold를 조정할 수 있다.

---

# Review Independence Rule

“생성한 agent가 스스로 5점”을 주는 것으로 검증하지 않는다.

독립성은 agent 개수보다 다음으로 만든다.
- 다른 rubric
- 다른 evidence view
- 원본 source에 재접근
- artifact를 생성한 prompt에 덜 의존
- 명시적 reject authority

Research writer와 fact reviewer가 같은 요약만 공유하면 독립 검증으로 보지 않는다.

---

# Review Outputs

Gate reviewer는 자연어 감상 대신 다음을 반환해야 한다.

- gate
- verdict: PASS / REVISE / REJECT / ESCALATE
- dimension scores
- blocking findings
- evidence
- exact artifact/unit affected
- requested revision
- whether re-review required

---

# Revision Loop Rule

REVISE:
- 오류 원인과 수정 대상이 명확할 때

REJECT:
- 주제/접근 자체가 기준에 부적합

ESCALATE:
- source conflict
- 비용 ceiling 충돌
- reconstruction truth 문제
- 두 기준이 상충해 자동 결정 불가능

같은 이유로 2회 이상 반복 실패하면 단순 retry를 중지하고 upstream design으로 rollback한다.

---

# Post-Publish Learning

시청 데이터가 quality scorecard를 대체하지 않는다.

예:
- 조회수 높고 factual score 낮음 → 성공으로 간주하지 않음
- 품질 높고 retention 낮음 → editorial/pacing 문제 조사

파일럿 이후 correlation 관찰:
- hook score vs first 30s retention
- coherence vs average percentage viewed
- visual explanatory score vs replay/comments
- production score vs human review time

scorecard는 데이터가 쌓이면 수정한다.

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
- Spatial/Asset Bible의 hard lock이 장면 사이에서 바뀜
- visual이 narration의 핵심 mechanism과 모순
- narration/script version mismatch가 의미를 바꿈
- 음악/SFX가 핵심 narration을 지속적으로 가리거나 잘못된 사실적 확신을 유도함
- 타 채널의 distinctive script/shot sequence를 지나치게 가깝게 모방
- 저작권/출처 provenance가 불명확한 핵심 자산
- music/SFX/voice/3D/footage의 핵심 commercial-use 권리가 unresolved
- title/thumbnail이 Evidence Pack보다 강한 사실 주장을 함

---

# Score Dimensions

## Q1. Factual Integrity — weight 12

5:
- major claim이 신뢰도 높은 source와 trace됨
- 상충 자료/불확실성이 명시됨
- 설명 단순화가 사실을 왜곡하지 않음

3:
- 대부분 추적 가능하나 일부 peripheral claim이 약함

0–2:
- source lineage 부재 또는 사실/추론 혼합

## Q2. Claim Provenance — weight 8

5:
`source → claim → script → visual/audio/package` 연결이 명확.

## Q3. Central Question & Payoff — weight 9

5:
- 첫 30–45초 안에 질문이 명확
- 결말에서 정확히 회수
- clickbait gap 없음

## Q4. Script Clarity — weight 8

5:
- 전문지식 없이 원리 추적 가능
- 인지 부하 제어
- 한 번에 한 핵심 개념
- qualifier가 이해 가능하게 유지됨

## Q5. Script ↔ Visual Alignment — weight 12

5:
- 주요 설명 문장마다 화면이 의미를 실제로 설명/증명
- B-roll 의존 낮음
- visual route가 설명 objective와 일치

## Q6. Spatial / Structural Continuity — weight 12

5:
- hard locks 유지
- orientation 이해 가능
- cutaway/explode/reassembly 일관
- system journey의 semantic anchor 유지

## Q7. Visual Explanatory Value — weight 8

5:
- 3D/2D/생성 영상이 없으면 이해하기 어려운 것을 실제로 명확하게 만듦
- tool spectacle가 explanation을 압도하지 않음

## Q8. Long-form Coherence — weight 6

5:
- 8–15분 전체가 하나의 질문으로 연결
- section 간 repetition/탈선 적음
- 정보 밀도와 휴지 구간이 균형

## Q9. Narration & Audio Intelligibility — weight 8

5:
- narration identity가 episode 간 일관
- proper noun/technical term pronunciation 정확
- music/SFX가 speech를 가리지 않음
- silence/score density가 정보 hierarchy를 지원

3:
- 대체로 이해되나 몇 구간에서 음악/발음/속도가 방해

0–2:
- narration이 피로하거나 이해에 실질적 장애

## Q10. Edit / Cross-Media Sync — weight 5

5:
- narration/visual/text/music/SFX가 같은 semantic beat를 지지
- picture edit가 causality/qualifier를 훼손하지 않음
- transition과 pacing이 공간 이해를 방해하지 않음

## Q11. Rights / Provenance Integrity — weight 5

5:
- 주요 visual/audio/voice/model asset의 source, terms review, commercial-use status가 추적 가능
- attribution/credits가 반영됨
- unresolved critical right가 없음

0–2:
- core asset rights 또는 provenance 불명확

## Q12. Packaging Integrity — weight 3

5:
- title/thumbnail이 central question을 명확히 약속
- final episode와 promise gap 없음
- factual nuance/reconstruction boundary를 부당하게 강화하지 않음

## Q13. Production Repeatability & Cost — weight 4

5:
- input/output artifact와 상태가 명확
- 특정 개인의 머릿속 정보에 의존하지 않음
- explanation value 대비 generation/review 비용이 합리적
- stale dependency / retry reason이 추적 가능

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

## Post / Audio Gate
- Narration & Audio Intelligibility >= 4
- Edit / Cross-Media Sync >= 4
- critical script-version mismatch = 0
- unresolved critical audio rights = 0

## Release Gate
- Rights / Provenance Integrity >= 4
- Packaging Integrity >= 4
- title/thumbnail factual escalation = 0
- caption critical errors = 0

## Final QA
- Weighted total >= 80
- Q1, Q5, Q6, Q9, Q11 each >= 4
- hard fail = 0

초기 파일럿을 본 뒤 threshold를 조정할 수 있다.

---

# Review Independence Rule

“생성한 agent가 스스로 5점”을 주는 것으로 검증하지 않는다.

독립성은 agent 개수보다 다음으로 만든다.
- 다른 rubric
- 다른 evidence view
- 원본 source/rights artifact에 재접근
- artifact를 생성한 prompt에 덜 의존
- 명시적 reject authority

Research writer와 fact reviewer가 같은 요약만 공유하면 독립 검증으로 보지 않는다.
Music creator가 자기 music rights를 최종 승인하는 것도 독립 검증으로 보지 않는다.
Packaging creator가 자기 factual escalation을 self-pass하는 것도 금지한다.

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
- upstream owner
- whether re-review required

---

# Revision Loop Rule

REVISE:
- 오류 원인과 수정 대상이 명확할 때

REJECT:
- 주제/접근 자체가 기준에 부적합

ESCALATE:
- source conflict
- rights uncertainty
- 비용 ceiling 충돌
- reconstruction truth 문제
- two quality criteria conflict and cannot be resolved automatically

같은 이유로 2회 이상 반복 실패하면 단순 retry를 중지하고 upstream design으로 rollback한다.

---

# Post-Publish Learning

시청 데이터가 quality scorecard를 대체하지 않는다.

예:
- 조회수 높고 factual score 낮음 → 성공으로 간주하지 않음
- CTR 높고 packaging integrity 낮음 → channel success로 승격하지 않음
- 품질 높고 retention 낮음 → editorial/pacing/audio density 문제 조사

파일럿 이후 correlation 관찰 후보:
- hook score vs first 30s retention
- coherence vs average percentage viewed
- visual explanatory score vs replay/comments
- audio intelligibility vs confusion/fatigue feedback
- packaging score vs CTR and promise-gap comments
- production score vs human review/rework time

scorecard는 데이터가 쌓이면 수정한다.
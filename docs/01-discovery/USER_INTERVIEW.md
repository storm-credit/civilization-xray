# User Intent Interview

이 문서는 사용자의 의도와 성공조건을 하네스/콘텐츠 설계 전에 고정하기 위한 인터뷰 기록이다.

## Interview Rule

- 질문은 의사결정 영향도가 높은 순서로 진행한다.
- 한 번에 너무 많은 질문을 던지지 않는다.
- 가능한 경우 3~4개 선택지를 주고, 사용자가 다른 답을 줄 수 있게 한다.
- 답이 없는 항목은 임의로 확정하지 않는다.
- 사용자의 답이 기존 가설과 충돌하면 기존 가설을 수정하고 `CHANGE_LOG.md`에 기록한다.

## Q1. Primary Goal — OPEN

Civilization X-Ray의 가장 중요한 1순위 목적은 무엇인가?

후보:
A. 유튜브 조회수/성장 가능성이 가장 높은 채널 만들기
B. 신비한 건축사전보다 더 정교하고 차별화된 고품질 AI 롱폼 만들기
C. 장기적으로 여러 채널/언어에 재사용 가능한 자동 제작 시스템 만들기
D. A+B+C를 모두 하되 우선순위를 정해 단계적으로 확장

결정: OPEN

## Q2. Primary Audience — OPEN

후보 축:
- 한국 일반 대중
- 10~30대 지식/과학/역사 시청자
- 가족/학생까지 이해 가능한 대중형
- 공학/건축에 관심 높은 준전문 시청자
- 글로벌 확장을 염두에 둔 language-neutral visual audience

결정: OPEN

## Q3. Content Center of Gravity — OPEN

후보:
A. 건축/구조공학 중심
B. 도시/인프라 중심
C. 역사 속 기술 중심
D. “문명의 숨은 구조” 상위 브랜드 아래 혼합

결정: OPEN

## Q4. Visual Truth Level — OPEN

질문:
실제 geometry/3D 모델을 써야 하는 장면과 생성형 AI로 충분한 장면의 경계를 어디에 둘 것인가?

후보:
A. 거의 전부 AI pseudo-3D
B. 핵심 Hero Object만 실제/반실제 geometry, 나머지는 AI
C. 구조 설명 장면은 geometry, 분위기/재구성은 AI
D. 사실상 full 3D pipeline + AI 보조

결정: OPEN

## Q5. Human-in-the-loop — OPEN

후보:
A. 주제/최종본만 승인
B. 주제 + 대본 + visual bible + 최종본 승인
C. 고비용 생성 직전마다 승인
D. 초기 시즌은 많이 검수하고 안정화 후 자동화 축소

결정: OPEN

## Q6. Long-form Length — OPEN

후보:
- 6–10분
- 8–15분
- 12–20분
- 주제에 따라 가변

결정: OPEN

## Q7. Publishing Cadence — OPEN

질문:
품질이 유지된다는 전제에서 목표 발행 주기는?

결정: OPEN

## Q8. Success Metrics — OPEN

후보 지표:
- CTR
- 첫 30초 retention
- average percentage viewed
- 평균 시청시간
- 조회수
- 구독 전환
- 댓글의 이해/신뢰 반응
- 제작비/분
- 제작시간/분
- 재생성률

결정: OPEN

## Q9. Accuracy Bar — OPEN

후보:
A. 대중 교양 수준: 신뢰 가능한 2차 출처 복수
B. 강한 팩트체크: 핵심 주장은 1차/공식/학술 우선
C. 다큐 수준: 모든 주요 claim에 provenance 유지

결정: OPEN

## Q10. Automation Goal — OPEN

후보:
A. 사람 중심 + AI 생산성 도구
B. 감독형 에이전트 파이프라인
C. episode brief만 넣으면 대부분 자동
D. 멀티채널/다국어까지 자동 운영

결정: OPEN

## Interview Exit Condition

모든 질문에 즉답할 필요는 없다.

다만 다음은 Harness Readiness 전에 반드시 닫혀야 한다.
- Primary Goal
- Primary Audience
- Content Center of Gravity
- Visual Truth Level
- Human-in-the-loop
- Accuracy Bar
- Automation Goal

나머지는 가설로 두더라도 검증 계획이 있어야 한다.

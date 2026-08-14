# Phase 0 Strategic Decisions

Status: **Director decision set for design completion**

사용자는 설계를 질문 대기 없이 끝까지 자동 진행하도록 승인했다. 따라서 미답 인터뷰 항목은 아래처럼 **가역적 설계 가설**로 닫는다. 실제 파일럿 데이터가 반박하면 `CHANGE_LOG.md`를 통해 변경한다.

## D1. Primary Goal

**Decision: staged A+B+C**

1. 먼저: 신뢰할 수 있고 정교한 한국어 롱폼 3D 설명 콘텐츠의 품질 기준을 만든다.
2. 다음: 반복 제작 가능한 감독형 하네스를 만든다.
3. 이후: 성과가 검증되면 다국어/멀티채널 자동화로 확장한다.

이유:
- 처음부터 완전 자동화를 최적화하면 품질 정의가 빈약한 상태에서 잘못된 과정을 자동화할 위험이 크다.
- 채널 성장만 최적화하면 Civilization X-Ray의 핵심 자산인 설명용 visual grammar가 약해질 수 있다.

## D2. Primary Audience

**Decision: 한국 일반 대중형 지식 시청자, 글로벌 확장 가능한 visual grammar**

초기 이해 수준:
- 공학 전공 지식 불필요
- 중학생 이상이면 핵심 원리를 따라갈 수 있는 설명
- 전문용어는 필요할 때만 쓰고 화면에서 즉시 해석

비목표:
- 전문가 강의
- 어린이 전용 교육
- 관광 가이드

## D3. Content Center of Gravity

4안:

| 안 | 중심 | 장점 | 단점 |
|---|---|---|---|
| A | 세계 건축물 | 소재가 익숙함 | 관광/상식 채널로 흐르기 쉬움 |
| B | 도시·인프라 | 숨은 구조를 보여주기 좋음 | 역사적 감정선이 약해질 수 있음 |
| C | 역사 속 기술 | 스토리와 갈등이 강함 | 검증 불확실성과 재구성 리스크 큼 |
| D | **문명의 숨은 구조** | 건축·도시·역사를 하나의 질문 문법으로 묶음 | 편집 규칙이 없으면 정체성 분산 가능 |

**Selected: D — 문명의 숨은 구조**

채널의 편집 원칙:
> 소재가 아니라 “보이지 않는 작동 원리”가 주인공이어야 한다.

## D4. Visual Truth Level

4안:

| 안 | 방식 | 평가 |
|---|---|---|
| A | 거의 전부 AI pseudo-3D | 빠르지만 구조 일관성/정확도 취약 |
| B | Hero Object만 geometry, 나머지 AI | 비용 균형 좋음 |
| C | **구조 설명은 geometry-backed, 분위기/역사 재구성은 AI** | 설명력·정교함·확장성 균형 최상 |
| D | 사실상 full 3D | 최고 통제력, 제작비/시간 과다 |

**Selected: C, with B allowed for simple episodes.**

핵심 원칙:
- 기둥/하중/수로/터널/기계적 동작처럼 topology가 설명의 근거인 컷은 geometry/depth/diagram 기반을 우선한다.
- 시대 분위기, 군중, 도시 establishing, 상상 재구성은 생성형 비주얼을 적극 활용한다.

## D5. Human-in-the-loop

**Selected: 초기에는 강한 감독형, 안정화 후 축소.**

초기 필수 승인:
1. Topic Lock
2. Claim/Research Lock
3. Script Lock
4. Hero Object / Visual Bible Lock
5. 고비용 generation batch 전
6. Final Publish

하네스가 반복적으로 통과하는 gate는 이후 자동 승인 후보가 된다.

## D6. Long-form Length

**Selected: 주제 가변, 기본 8–15분.**

길이를 목표로 원고를 늘리지 않는다. 한 질문이 설명 완료되는 시점이 종료점이다.

## D7. Publishing Cadence

**Selected: Phase 1 pilot 전 고정하지 않음.**

이유:
- 제작 속도를 아직 모르는 상태에서 주 2회/3회 등을 목표로 박으면 품질을 역으로 훼손할 수 있다.

파일럿 3편 이후:
- median human review time
- regeneration rate
- cost/minute
- production lead time

을 보고 cadence를 결정한다.

## D8. Success Metrics

### Pre-publish quality metrics
- Factual integrity
- Claim provenance completeness
- Script clarity
- Script ↔ Visual alignment
- Spatial continuity
- Visual explanatory value
- Long-form coherence
- Re-generation rate
- Human review burden
- Cost/minute

### Post-publish audience metrics
- CTR
- first 30s retention
- average percentage viewed
- average view duration
- subscriber conversion
- comments indicating comprehension/trust

조회수 단독으로 품질을 정의하지 않는다.

## D9. Accuracy Bar

**Selected: documentary-grade provenance for major claims.**

- 핵심 claim: 공식/1차/학술/전문기관 우선
- 2차 출처는 탐색과 교차검증에 사용
- 사실/추론/재구성/설명용 단순화를 구분
- source lineage를 script와 visual까지 연결

## D10. Automation Goal

**Selected: supervised agent pipeline first; high automation later.**

목표:
- Phase 1: 사람이 고비용/고위험 gate를 승인
- Phase 2: 안정된 gate의 자동화
- Phase 3: episode brief → 대부분 자동 + exception review
- Phase 4: 필요 시 다국어/멀티채널

## Decision Review Trigger

다음 데이터 중 하나가 현재 가설을 강하게 반박하면 재검토한다.
- 파일럿 3편의 제작비/시간
- continuity 실패율
- 사실 오류 발견률
- viewer retention 패턴
- AI 모델 capability 변화
- 사용자가 콘텐츠 방향을 변경

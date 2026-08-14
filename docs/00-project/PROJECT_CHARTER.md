# Civilization X-Ray — Project Charter

## Status

- Phase: 0 — Discovery & Design
- Implementation: **Not allowed yet**
- Primary output of this phase: validated content/visual system design + harness-ready specification

## Core Thesis

Civilization X-Ray는 세계의 건축물·도시·역사·인프라를 나열하는 채널이 아니라, 사람들이 익숙하게 보지만 내부 원리는 잘 모르는 문명 구조를 “X-Ray처럼 해부”하는 롱폼 시각 다큐멘터리 시스템을 목표로 한다.

초기 범위 후보:
- Architecture
- Cities
- Infrastructure
- Historical engineering
- Transport systems
- Mega structures
- Hidden urban systems

범위는 넓게 열어 두되, 하나의 채널 정체성이 흐려지는 문제를 Discovery에서 검증한다.

## Working Content Formula

현재 가설:

> Familiar object/system + unresolved question + hidden mechanism + visual reveal + evidence-backed explanation

예:
- 베네치아는 왜 가라앉지 않는가?
- 초고층은 강풍에 왜 부러지지 않는가?
- 고대 로마는 펌프 없이 어떻게 물을 보냈는가?
- 바다 밑 터널은 양쪽에서 파고 어떻게 만났는가?

이 공식은 확정안이 아니다. 레퍼런스 분석 후 수정할 수 있다.

## What We Are Optimizing For

우선순위 후보이며 사용자 인터뷰에서 확정한다.

1. 설명의 명확성
2. 시각적 정교함
3. 장면 간 구조 일관성
4. 롱폼 유지력
5. 사실 정확성 / 출처 추적성
6. 제작 반복 가능성
7. AI 자동화 가능성
8. 비용 대비 품질
9. 채널 고유성

## Explicit Non-Goals for Phase 0

- 앱/웹 UI 구현
- 영상 생성 API 연결
- Blender 자동화 구현
- 유튜브 업로드 자동화
- 에이전트 개수부터 고정하기
- 특정 영상 모델을 영구 표준으로 선정하기
- 예쁜 AI 이미지 몇 장을 연결한 슬라이드쇼 파이프라인 만들기
- 레퍼런스 채널의 제목/구도/스크립트를 그대로 복제하기

## Phase 0 Questions

### Audience
- 핵심 시청자는 누구인가?
- 한국어 단일 채널인가, 다국어 확장을 전제로 하는가?
- 공학 지식 수준을 어디에 맞추는가?

### Editorial
- 건축/도시/역사 중 어느 축이 브랜드의 중심인가?
- 한 편은 한 질문인가, 하나의 구조물을 여러 질문으로 파는가?
- 목표 길이와 평균 정보 밀도는?

### Visual
- “실제 3D 모델 기반”과 “AI 기반 pseudo-3D”의 경계는 어디인가?
- 반드시 geometry가 필요한 장면은 어떤 유형인가?
- Hero Object continuity를 어떤 수준까지 강제할 것인가?

### Research
- 역사·공학 주장의 출처 등급은 어떻게 나눌 것인가?
- 자료가 불완전한 고대 구조를 어떻게 시각화할 것인가?
- 재구성 장면에 어떤 표시/표현 규칙을 둘 것인가?

### Production
- 사람의 승인 지점은 어디인가?
- 품질과 비용이 충돌할 때 어느 쪽을 우선하는가?
- 월/주 제작량 목표는 어느 정도인가?

### Automation
- 완전 자동화가 목표인가, 감독형 반자동화가 목표인가?
- 어떤 단계는 반드시 인간이 통제해야 하는가?
- 모델/벤더가 바뀌어도 유지되는 시스템 경계는 무엇인가?

## Phase 0 Exit Criteria

Phase 0는 아래가 모두 증거와 함께 충족되어야 끝난다.

- 사용자 인터뷰 기록
- 레퍼런스 분석 프레임워크
- 대표 레퍼런스 역설계 결과
- 콘텐츠 포지셔닝 4안
- 시각 시스템 4안
- 맹점 훑기 보고서
- pre-mortem / 함정 체크
- 성공조건 scorecard
- harness readiness review
- harness architecture 4안
- 권고 하네스 구조와 책임/계약 정의
- 변경 결정 로그
- 사용자 승인

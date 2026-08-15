# Reference Methods Map

이 문서는 참고 저장소에서 Civilization X-Ray에 가져올 **원리**와 가져오지 않을 **구현 종속성**을 구분한다.

## 1. Karpathy Guidelines

Reference: `multica-ai/andrej-karpathy-skills`

가져올 원리:
- 구현 전 가정 공개
- 다중 해석이 있으면 숨기지 않기
- 더 단순한 안이 있으면 제시하기
- 최소 변경 / 과설계 방지
- 검증 가능한 성공조건
- 완료 주장 전 증거 확인

Civilization X-Ray 적용:
- 영상 제작 시스템을 처음부터 거대 멀티에이전트 플랫폼으로 만들지 않는다.
- 하네스는 실제 workflow에서 필요한 책임만 둔다.
- 디자인 결정은 “멋있다”가 아니라 검증 가능한 기준에 연결한다.

가져오지 않을 것:
- 코딩 작업용 예시를 콘텐츠 제작 workflow에 그대로 복사하지 않는다.

## 2. Superpowers

Reference: `obra/superpowers`

가져올 원리:
- 새 프로젝트는 architectural discovery를 먼저 수행
- 브레인스토밍/설계/사용자 승인 전 구현 금지
- 질문 → 대안 비교 → written design → self-review → 승인 → plan 순서
- 복잡성이 발견되면 더 무거운 설계 경로로 upgrade
- evidence before completion

Civilization X-Ray 적용:
- Design Gate를 CLAUDE.md 최상위 규칙으로 둔다.
- 콘텐츠 포지셔닝, visual grammar, harness architecture 모두 먼저 설계한다.
- 하네스 설계 자체도 4안 비교와 승인 과정을 거친다.

가져오지 않을 것:
- software TDD workflow를 영상 제작에 문자 그대로 적용하지 않는다.
- 대신 artifact-specific validation으로 변환한다.

## 3. claude-video

Reference: `bradautomates/claude-video`

가져올 원리:
- 영상 이해는 transcript만으로 충분하지 않다.
- timestamped transcript와 실제 frame/scene을 함께 분석한다.
- 긴 영상은 전체 sparse scan 후 중요한 구간을 집중 분석한다.
- frame budget / dedup / focused windows처럼 비용과 정보량을 관리한다.

Civilization X-Ray 적용:
- 레퍼런스 영상 역설계 단계에서 transcript ↔ frame alignment를 기본 artifact로 둔다.
- 10분+ 영상은 전체 구조 scan과 hook/핵심 reveal/ending의 dense pass를 구분한다.
- “무엇을 말했나”와 “무엇을 보여줬나”를 동일 timeline 위에 놓는다.

가져오지 않을 것:
- 현재 구현 세부사항이나 특정 transcription provider를 하네스 핵심 계약으로 고정하지 않는다.

## 4. Understand-Anything

Reference: `Lum1104/Understand-Anything` 및 프로젝트의 현재 계보

가져올 원리:
- 복잡한 대상을 파일/기능 단위가 아니라 관계 그래프로 이해
- multi-agent 분석 시 각 분석 단위와 dependency를 명시
- “복잡해 보이는 그래프”보다 “어떻게 연결되는지 가르치는 구조”를 우선

Civilization X-Ray 적용:
- reference channel 분석을 영상별 메모 집합으로 끝내지 않는다.
- 반복되는 관계를 grammar로 추출한다.
  - hook type
  - claim type
  - visual action type
  - camera action
  - reveal pattern
  - evidence type
- 장차 episode artifact graph / claim lineage 설계에 참고한다.

가져오지 않을 것:
- code knowledge graph 스키마를 그대로 콘텐츠 graph로 복제하지 않는다.

## 5. agentmemory

Reference: `rohitg00/agentmemory`

가져올 원리:
- 세션을 넘어 지속되는 기억
- 반복 설명/반복 실수 감소
- 필요한 기억만 검색해 context에 주입
- 단순 고정 instruction file만으로 모든 기억을 해결하지 않기

Civilization X-Ray 적용:
- Channel DNA와 Episode State를 분리
- accepted/rejected decisions와 이유를 기억
- 모델/프롬프트 실패 패턴을 기억
- source/confidence/version/scope가 있는 memory를 지향

가져오지 않을 것:
- Phase 0에서 메모리 서버를 설치하거나 구현하지 않는다.
- 실제 필요 artifact와 retrieval use-case가 나오기 전 기술을 선택하지 않는다.

---

# Empirical Reference Role Split

`docs/09-validation/REFERENCE_ROLE_MATRIX_V1.md`의 2026-08-15 empirical update를 따른다.

역할 분리:
- `신비한 건축사전` → Korean short-form packaging / hook / compressed mechanism grammar
- Practical Engineering → long-form civil-engineering explanation clarity
- The B1M → long-form construction / mega-project story / scale framing
- Lesics → 3D engineering mechanism visualization

핵심 규칙:
- 한 레퍼런스가 packaging, pacing, visual grammar, factual authority를 모두 소유하지 않는다.
- short-form 성과를 8–15분 long-form pacing 근거로 직접 전이하지 않는다.
- direct frame/transcript를 보지 못한 항목은 camera cadence나 production tool을 추측하지 않는다.
- benchmark observation은 `OBSERVED_DIRECT | OBSERVED_PUBLIC_INDEX | OBSERVED_REPOST | INFERRED | UNOBSERVED` 중 하나로 표시한다.

---

# Reference Review Rule

새 레퍼런스를 추가할 때 반드시 기록:
1. 무엇을 참고하는가?
2. 왜 참고하는가?
3. 어떤 원리를 추출하는가?
4. 어떤 부분은 의도적으로 가져오지 않는가?
5. 라이선스/권리 이슈가 있는가?
6. 우리 성공조건 중 무엇을 개선하는가?

# Anti-Copy Rule

- 레퍼런스 영상의 문장/구성/샷을 그대로 복제하지 않는다.
- tool choice를 “그 채널도 쓸 것 같다”는 추측으로 확정하지 않는다.
- 공개 근거가 없는 제작 툴은 `hypothesis`로 표시한다.
- 분석의 목표는 **channel DNA를 복사하는 것**이 아니라 **explanatory grammar를 이해하고 우리 포맷으로 재설계하는 것**이다.

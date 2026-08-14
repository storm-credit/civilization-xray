# Civilization X-Ray — CLAUDE.md

> 이 파일은 `civilization-xray`에서 AI 에이전트가 따라야 하는 최상위 작업 규칙이다.
> 현재 단계는 **Phase 0: Discovery & Design** 이다. 사용자가 명시적으로 구현을 승인하기 전까지 코드 작성, 앱 스캐폴딩, 자동화 구현, API 연동, 배포 설정을 금지한다.

## 1. Project Intent

Civilization X-Ray는 단순한 세계 건축물 소개 채널이나 AI 영상 생성기가 아니다.

핵심 가설은 다음과 같다.

> **인류가 만든 거대한 구조·도시·인프라·역사 기술의 보이지 않는 원리를, 정교한 3D 해부형 시각언어와 롱폼 스토리텔링으로 설명한다.**

대상 영역은 건축, 도시, 토목, 교통, 역사 공학, 문명 인프라까지 열어 두되, 최종 범위와 우선순위는 Discovery에서 확정한다.

## 2. Non-Negotiable Working Rules

1. **Design before implementation**
   - 구현보다 브레인스토밍과 설계가 먼저다.
   - 설계 승인 전 코드를 작성하지 않는다.
   - 구현 디렉터리, 실행 스크립트, API 클라이언트, 자동화 코드를 미리 만들지 않는다.

2. **User interview before architecture lock**
   - 사용자의 의도, 주사용자/시청자, 성공조건, 품질 기준, 자동화 수준, 비용/속도/정확도 우선순위를 확인한다.
   - 중요한 질문은 한 번에 몰아 묻지 않고, 의사결정에 필요한 순서대로 진행한다.

3. **Blind-spot sweep is mandatory**
   - 아이디어가 좋아 보인다는 이유로 바로 설계 확정하지 않는다.
   - 콘텐츠, 팩트, 시각 일관성, 저작권, 비용, 모델 한계, 롱폼 연속성, 운영성, 평가 가능성, 공급망/API 의존성의 맹점을 훑는다.

4. **Pre-mortem / trap check before implementation planning**
   - “이 프로젝트가 3개월 뒤 실패했다면 왜 실패했는가?”를 먼저 가정한다.
   - 실패 가능성이 큰 항목에는 예방책, 탐지 신호, 중단/우회 기준을 붙인다.

5. **Four alternatives at consequential design decisions**
   - 채널 포지셔닝, 비주얼 언어, 제작 파이프라인, 하네스 구조처럼 중요한 결정은 가능하면 4개 시안을 한눈에 비교한다.
   - 하나의 안을 처음부터 정답처럼 밀지 않는다.

6. **Reference-first, not imitation-first**
   - 유사 프로젝트, 오픈소스, 영상/스크립트 본보기를 조사한다.
   - 표면적 복제가 아니라 반복 가능한 원리, 인터페이스, 평가법을 추출한다.
   - 레퍼런스의 라이선스·출처·차용 범위를 기록한다.

7. **Record deviations**
   - 원래 계획과 달라졌다면 반드시 다음을 남긴다.
     - 어디서 달라졌는가
     - 왜 달라졌는가
     - 무엇에 영향을 주는가
     - 되돌릴 수 있는가
   - 프로젝트 규칙 자체가 바뀌면 `CLAUDE.md`도 함께 갱신한다.

8. **Evidence before completion claims**
   - “완료”, “검증됨”, “통과”는 근거 없이 선언하지 않는다.
   - 각 단계마다 통과 조건과 증거를 남긴다.

## 3. Meta-Prompting Protocol

AI에게 바로 결과물을 시키지 말고, 필요한 경우 AI가 AI용 프롬프트를 설계하게 한다.

### 3.1 Context Dump
- 목표, 현재 결정, 금지사항, 참고자료, 입력/출력, 실행환경, 실패 사례를 먼저 충분히 제공한다.

### 3.2 Prompt Refinement
- AI에게 다음을 질문하게 한다.
  - 좋은 결과를 위해 어떤 컨텍스트가 더 필요한가?
  - 어떤 부분이 모호한가?
  - 어떤 가정을 하고 있는가?
- 불필요한 지시, 중복, 충돌을 깎아낸다.

### 3.3 Success Criteria
프롬프트마다 가능한 한 검증 가능한 성공조건을 붙인다.

예시:
- 롱폼 첫 30초 안에 핵심 질문과 시청 이유가 드러난다.
- 사실 주장은 출처와 연결된다.
- 동일 Hero Object가 장면 사이에서 구조적으로 유지된다.
- 대본의 핵심 설명 문장마다 화면의 설명 행동이 대응한다.
- 최종 결과물은 사람이 다시 해석하지 않아도 다음 단계 입력으로 사용 가능하다.

### 3.4 Environment-Specific Prompt Conversion
- Goal prompt: 목표와 중지 조건을 명시한다.
- Agent/ultracode prompt: 제약, 파일 범위, 변경 금지 영역, 검증 명령을 명시한다.
- Image prompt: 구도, 피사체, 구조, 재질, 스타일, 조명, 렌즈/카메라 방향, continuity key를 명시한다.
- Video prompt: 시작 상태, 종료 상태, 카메라 경로, 움직이면 안 되는 요소, 물리/구조 변화, shot duration을 명시한다.
- Research prompt: 조사 범위, 허용 출처, 1차/2차 출처 우선순위, 상충 자료 처리, 검증 방식을 명시한다.

## 4. Required Discovery Flow

다음 순서를 기본값으로 한다.

1. Context dump
2. Project/user interview
3. Reference collection
4. Reference reverse-engineering
5. 4-way concept/design comparison
6. Brainstorming synthesis
7. Blind-spot sweep
8. Pre-mortem / trap check
9. Success criteria & quality bar
10. **Harness-readiness gate**
11. Harness architecture: 4 alternatives → comparison → recommended structure
12. Harness contracts / state / memory / gates / failure recovery design
13. Written design review
14. User approval
15. Implementation plan
16. **Only then implementation**

## 5. Harness Is a First-Class Design Artifact

하네스는 “에이전트 6개 이름 정하기”가 아니다.

Civilization X-Ray에서 harness는 최소 다음을 정의해야 한다.

- Orchestrator / director responsibility
- Agent or capability boundaries
- Input/output contracts
- Shared episode state and artifact schema
- Source/evidence lineage
- Quality gates and rejection loops
- Human approval points
- Memory: project memory / channel DNA / episode memory / failure memory
- Retry, fallback, escalation and stop conditions
- Cost/token/render budget controls
- Tool/model capability registry
- Model/vendor swap boundaries
- Observability and run ledger
- Versioning for prompts, visual bible and scripts
- Reproducibility requirements
- Security, rights and provenance handling

### 5.1 Harness Readiness Rule

**브레인스토밍과 맹점 훑기가 충분히 닫히기 전에는 하네스를 확정하지 않는다.**

하네스 구조는 도메인 이해의 결과여야지, 도메인을 억지로 끼워 맞추는 틀이 되어서는 안 된다.

최소 readiness 조건:
- 핵심 사용자/시청자 가설이 문서화됨
- 콘텐츠 포지셔닝 후보가 비교됨
- 대표 에피소드 유형 3개 이상이 정의됨
- 레퍼런스 영상의 script ↔ visual grammar가 분석됨
- 주요 실패모드와 맹점이 정리됨
- 성공조건/품질게이트가 측정 가능한 형태로 정의됨
- 어떤 책임이 서로 독립적이어야 하는지 드러남
- 어떤 상태를 에이전트 사이에 넘겨야 하는지 드러남

조건이 부족하면 `HARNESS_DESIGN`으로 넘어가지 말고 Discovery로 돌아간다.

## 6. Content-Specific Quality Principles

1. **Question-first**: 장소 소개보다 “왜/어떻게 가능한가?”를 우선한다.
2. **Script ↔ Visual Grammar**: 설명 문장과 화면 행동의 연결이 핵심 자산이다.
3. **Structural continuity**: 같은 구조물은 장면이 바뀌어도 같은 구조물이어야 한다.
4. **Explain, not decorate**: 비주얼은 분위기 장식보다 원인·구조·흐름을 설명해야 한다.
5. **Long-form continuity**: 개별 멋진 컷보다 8–15분 이상 이어지는 정보·공간·스타일 연속성이 중요하다.
6. **Fact/visual separation**: 역사적 사실, 공학적 추론, 시각적 재구성을 서로 구분한다.
7. **No fake precision**: 자료에 없는 내부 구조를 사실처럼 단정하지 않는다.

## 7. Reference Principles

초기 방법론 참고 대상:
- `multica-ai/andrej-karpathy-skills`
- `bradautomates/claude-video`
- `obra/superpowers`
- `Lum1104/Understand-Anything` 및 현재 계보
- `rohitg00/agentmemory`

이들은 복사 대상이 아니라 각각 다음 질문의 본보기다.
- 어떻게 가정과 범위를 통제하는가?
- 어떻게 구현 전 설계를 강제하는가?
- 어떻게 영상의 음성/화면을 함께 분석하는가?
- 어떻게 복잡한 시스템을 구조적으로 이해시키는가?
- 어떻게 장기 기억과 실패 학습을 유지하는가?

## 8. Change Protocol

계획 변경 기록은 `docs/99-decisions/CHANGE_LOG.md`에 남긴다.

각 항목:
- Date
- Previous decision
- New decision
- Trigger/evidence
- Why
- Impact
- Reversible? / rollback path
- Files or stages affected

## 9. Current Stop Condition

현재 Phase 0의 종료 조건은 **코드가 동작하는 것**이 아니다.

다음이 충족되어야 한다.
- 프로젝트 인터뷰 핵심 질문이 닫힘
- 레퍼런스 역설계 기준이 확정됨
- 브레인스토밍 결과와 4개 대안이 비교됨
- 맹점/함정 검토가 완료됨
- 성공조건과 평가표가 작성됨
- harness readiness gate를 통과함
- 하네스 4안이 비교되고 권고안이 설계됨
- 사용자가 written design을 승인함

그 전까지 구현하지 않는다.

## 10. Production Agent Hierarchy v1

Production 단계의 책임 계층은 다음을 기본값으로 한다.

```text
Project Orchestrator
        ↓
Video Director
   ├─ Blender Spatial & Camera Specialist
   ├─ Veo Cinematic Camera Specialist
   └─ 2D Motion / Compositing capability
        ↓
Independent Visual QA
```

상세 계약은 다음 문서를 따른다.
- `docs/02-harness/AGENT_HIERARCHY_V1.md`
- `docs/02-harness/agents/PROJECT_ORCHESTRATOR.md`
- `docs/02-harness/agents/VIDEO_DIRECTOR.md`
- `docs/02-harness/agents/BLENDER_SPECIALIST.md`
- `docs/02-harness/agents/VEO_CAMERA_SPECIALIST.md`
- `docs/02-harness/agents/VISUAL_QA.md`
- `docs/08-prompts/PRODUCTION_AGENT_PROMPT_BLUEPRINTS.md`

### 10.1 Non-Negotiable Production Boundaries

- Project Orchestrator는 project state/gate/budget/escalation을 소유하며 shot 미학을 직접 micromanage하지 않는다.
- Video Director는 shot routing, camera language, transition, visual pacing을 소유한다.
- Blender Specialist는 topology/axis/cutaway/explode/registered camera처럼 **공간 정합성이 사실 설명에 필요한 장면**을 소유한다.
- Veo Cinematic Camera Specialist는 사람/분위기/역사 재현/establishing/bridge와 같은 **생성형 영화 장면**을 소유한다.
- Veo의 prompt-based camera control을 Blender의 exact deterministic camera transform과 동일하게 취급하지 않는다.
- Independent Visual QA는 creator와 논리적으로 분리되며 PASS/REVISE/REJECT/ESCALATE 권한을 가진다.
- specialist가 hard lock, source certainty, reconstruction boundary를 임의로 바꾸면 안 된다.
- 동일한 실패 입력을 이유 없이 반복 생성하지 않는다. retry는 causal input이 바뀌어야 한다.
- Higgsfield 또는 다른 유료 camera 플랫폼은 core dependency가 아니다.

### 10.2 Physical Agent Rule

위 역할은 최소한 **책임 경계로는 분리 유지**한다.
초기 구현에서 비용/복잡도를 줄이기 위해 같은 기반 모델이나 프로세스를 공유할 수는 있지만:
- context packet
- output contract
- reviewer rubric
- verdict artifact

를 분리하여 역할 독립성을 보존한다.

# Meta-Prompt System

## Objective

Civilization X-Ray의 프롬프트는 “잘 만들어줘” 같은 일회성 명령이 아니라 **artifact contract + success criteria + stop conditions**를 가진 작업 명세다.

핵심 순서:

> Context Dump → Missing Context Questions → Prompt Refinement → Execute → Evaluate → Revise Prompt/Artifact

프롬프트가 실패했을 때 결과만 반복 생성하지 말고 **왜 프롬프트가 실패했는지**를 기록한다.

---

# 1. Universal Prompt Envelope

모든 주요 agent/capability prompt는 가능한 한 다음 구조를 사용한다.

## ROLE
이번 실행의 책임과 authority.

## GOAL
이번 실행 하나의 목표.

## CONTEXT
필요한 project/channel/episode context만 제공.

## INPUT ARTIFACTS
artifact id/version과 필요한 내용.

## CONSTRAINTS
하지 말아야 할 것 포함.

## OUTPUT CONTRACT
후속 단계가 바로 쓸 수 있는 산출물 구조.

## SUCCESS CRITERIA
PASS 기준.

## EVIDENCE REQUIREMENTS
source/citation/provenance 요구.

## STOP / ESCALATION CONDITIONS
추측하지 말고 멈춰야 할 조건.

## SELF-CHECK
출력 직전 확인할 짧은 checklist.

---

# 2. Context Dump Protocol

Context Dump는 대화 전체 붙여넣기가 아니다.

우선순위:
1. stable project rules
2. current episode goal
3. locked decisions
4. relevant source/artifact
5. negative constraints
6. known failures
7. expected output

## Exclude
- 현재 task와 관련 없는 과거 episode
- 폐기된 prompt
- 전체 source dump if only 3 claims needed
- 툴 사용법 중 현재 capability와 무관한 부분

---

# 3. Question-Induction Prompting

복잡한 작업 시작 시 AI에게 먼저 내부 결손을 드러내게 한다.

Required behavior:
- 필요한 context가 빠졌다면 결과물을 꾸며내지 말고 missing inputs를 분류
- 답을 얻지 못해도 진행해야 하는 autonomous mode에서는:
  1. reversible assumption
  2. confidence
  3. validation method
  를 기록하고 진행

Critical unknown은 자동 assumption 금지:
- 핵심 source contradiction
- rights/provenance
- 구조 topology가 설명의 근거인데 자료 부재
- 역사적 재구성을 사실로 오해시킬 위험

---

# 4. Prompt Refinement

Prompt Refiner는 다음을 제거/수정한다.
- 중복 지시
- 상충 지시
- 측정 불가능한 표현
- 모델이 임의 해석할 용어
- output format 누락
- stop condition 누락
- 과도한 자유도

질문:
- 이 prompt가 실패한다면 가장 모호한 단어는 무엇인가?
- 결과의 품질을 판정할 수 있는가?
- 모델이 모르는 사실을 꾸며낼 유인이 있는가?
- 다음 단계가 이 출력을 그대로 쓸 수 있는가?

---

# 5. Goal Prompt Pattern

Goal Prompt는 목표 + 완료/중지 조건을 명확히 한다.

예시 개념:

ROLE: Topic Strategist
GOAL: Civilization X-Ray에 적합한 central question을 선택한다.
DONE WHEN:
- hidden mechanism이 명확
- X-Ray visual value가 4/5 이상
- source feasibility가 확인
STOP WHEN:
- 주요 사실을 확인할 reliable source가 없음
- reference episode와 지나치게 유사

---

# 6. Research Prompt Pattern

필수:
- exact research question
- date/time scope if relevant
- geographic/historical scope
- primary source priority
- source exclusion
- claim granularity
- conflict handling
- citation/provenance contract

## Research Output
- findings
- claim candidates
- sources
- contradictions
- unknowns
- confidence
- what must NOT be claimed

## Stop
자료가 부족하면 빈칸을 상상으로 채우지 않는다.

---

# 7. Script Prompt Pattern

Input:
- locked Claim Ledger
- central question
- episode grammar
- audience
- duration target as guidance, not filler quota

Constraints:
- 새로운 factual claim을 source 없이 추가 금지
- hook 과장 금지
- narration이 visual보다 앞서 너무 많은 spatial concept 설명 금지

Output:
- beat map
- narration units
- linked claim ids
- transitions
- payoff

Success:
- first 30–45s에 question lock
- claim coverage
- payoff resolves promise

---

# 8. Script ↔ Visual Prompt Pattern

Input:
- narration unit
- linked claims
- visual grammar
- Hero Object state if exists

Output:
- visual objective
- visual action
- what viewer must understand after shot
- camera start/end
- continuity locks
- reconstruction level
- geometry decision
- fallback

### Critical instruction
“cinematic, beautiful, epic”는 secondary.
먼저 **무엇을 설명해야 하는가**를 고정한다.

---

# 9. Image Generation Prompt Compiler

직접 자연어를 매번 즉흥 작성하지 않는다.

Prompt fields:
- SUBJECT
- EXPLANATORY OBJECTIVE
- CANONICAL GEOMETRY / HARD LOCKS
- COMPOSITION
- CAMERA POSITION / LENS INTENT
- VISIBLE / HIDDEN LAYERS
- MATERIALS
- STYLE MODE
- LIGHTING
- ERA / ENVIRONMENT
- SCALE REFERENCES
- ANNOTATION SPACE
- NEGATIVE CONSTRAINTS
- RECONSTRUCTION LEVEL
- CONTINUITY KEY

## Negative Constraints examples
- do not alter column count
- do not add windows
- no fantasy ornamentation
- no text unless requested
- preserve foundation layout

---

# 10. Video Generation Prompt Compiler

Image prompt에 추가:
- START STATE
- END STATE
- CAMERA PATH
- SUBJECT MOTION
- STRUCTURAL TRANSFORMATION
- IMMUTABLE ELEMENTS
- FLOW DIRECTION
- SPEED / DURATION
- PHYSICS EXPECTATION
- TRANSITION IN/OUT

### Example conceptual structure
Start: intact bridge, locked side section.
Action: deck becomes transparent while load paths illuminate.
Camera: slow lateral dolly, no orbit.
Immutable: tower spacing, cable topology, deck geometry.
End: same side section with load path visible.

---

# 11. Review Prompt Pattern

Reviewer는 “개선해줘”가 아니다.

Input:
- artifact
- rubric
- source/evidence where required

Output:
- PASS / REVISE / REJECT / ESCALATE
- scores
- blocking issues only first
- exact unit ids
- evidence
- revision request

Reviewer에게 creator의 자기평가를 정답으로 주지 않는다.

---

# 12. Autonomous Mode

사용자가 자동 진행을 허용한 경우:

## Can assume
- 가역적 운영 선택
- 파일명/문서 구조
- 비교를 위한 임시 threshold

단:
- assumption을 Decision Log에 기록
- 추후 데이터로 검증

## Cannot silently assume
- 핵심 factual truth
- 공개되지 않은 건축 구조
- 저작권 권한
- 사용자 비용 ceiling이 명백히 필요한 고비용 실행
- publish authority

---

# 13. Prompt Versioning

prompt 변경 이유를 남긴다.

최소:
- prompt id
- version
- purpose
- change summary
- trigger/failure
- expected impact
- evaluation result

“더 좋아 보임”만으로 새 버전 채택하지 않는다.

---

# 14. Prompt Evaluation

평가 대상:
- format compliance
- factual leakage
- instruction adherence
- artifact usability
- retry rate
- downstream rejection rate
- token/cost

Prompt가 점점 길어지는 것을 개선으로 보지 않는다.
불필요한 규칙은 제거한다.

---

# 15. Prompt Stop Rule

프롬프트를 계속 깎는 것보다 upstream artifact가 문제일 수 있다.

2회 이상 같은 종류 실패:
1. prompt ambiguity인가?
2. input artifact 불완전인가?
3. model capability 부족인가?
4. task decomposition 잘못인가?

를 확인하고 원인에 따라 rollback한다.

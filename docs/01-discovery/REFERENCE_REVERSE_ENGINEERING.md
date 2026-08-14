# Reference Reverse Engineering Protocol

## Purpose

레퍼런스 채널을 보고 “이런 느낌으로 만들자”라고 끝내지 않는다.

목표는 다음 관계를 데이터로 뽑는 것이다.

> **Question → Script Beat → Claim → Visual Action → Camera → Transition → Viewer Payoff**

특히 사용자가 제시한 `신비한 건축사전` 계열의 정교함을 평가할 때 transcript만 분석하는 것을 금지한다.

---

# Benchmark Corpus

초기 corpus 권장 규모: **10편**

선정 기준:
- 최근/대표 영상 혼합
- 6분 이상 롱폼 우선
- 구조물/도시/교통/수리/역사 공학 등 다른 주제
- 조회 성과가 높은 영상과 보통 영상 혼합
- 단면/분해/flow/역사 재구성 등 visual grammar가 다른 편

사용자가 제공한 영상 URL은 anchor reference로 포함한다.

## Why 10

1–2편만 보면 해당 소재의 우연한 연출을 channel DNA로 오판할 수 있다.
10편 정도면 반복되는 문법과 주제별 예외를 분리하기 시작할 수 있다.

20편 이상은 초기 설계 단계에서 비용 대비 수익이 낮을 수 있으므로, 10편 분석 후 필요 시 확장한다.

---

# Analysis Passes

## Pass 1 — Metadata / Promise

기록:
- title
- thumbnail promise
- duration
- topic
- central question
- expected answer before watching

분석:
- 제목이 대상 중심인가, mechanism 중심인가?
- 제목이 실제 payoff와 일치하는가?

## Pass 2 — Transcript Structure

timestamp별로 구분:
- hook
- setup
- constraint
- claim
- explanation
- reveal
- transition
- historical context
- recap
- payoff

대본을 단순 문장 목록으로 저장하지 않고 beat boundary를 기록한다.

## Pass 3 — Visual Structure

scene/keyframe을 timestamp transcript와 맞춘다.

기록:
- visual subject
- shot type
- camera move
- cutaway/explode/transparency 여부
- overlay type
- object continuity state
- background/era
- scene duration

## Pass 4 — Script ↔ Visual Alignment

각 중요한 narration unit에 대해:
- 화면이 같은 내용을 보여주는가?
- 화면이 한 단계 더 설명하는가?
- 단순 B-roll인가?
- visual proof인가?
- narration과 화면의 reveal timing은 어떻게 맞는가?

## Pass 5 — Spatial Grammar

특히 기록:
- 최초 축 설정 시점
- 단면 방향
- orbit 방향
- 외부→내부 이동 방식
- scale change
- component removal
- reassembly
- flow direction
- 같은 Hero Object 유지 여부

## Pass 6 — Attention Rhythm

15–30초 단위로:
- 새 정보
- 새 visual transformation
- scale change
- question/reset
- emotional beat

를 표시한다.

목표는 “몇 초마다 컷” 같은 표면 공식이 아니라 **인지적 새로움이 언제 공급되는가**를 보는 것이다.

## Pass 7 — Sound / Narration

- narration speed
- pause before/after reveal
- music intensity shift
- mechanical/impact/water/wind SFX
- silence usage

sound가 구조 이해를 돕는지, 단순 장식인지 구분한다.

## Pass 8 — Truth / Reconstruction

화면별로 가능한 경우:
- documented
- inferred
- reconstructed
- illustrative

를 판단한다.

제작 툴은 공개 근거가 없는 한 단정하지 않는다.
`observed visual behavior`와 `tool hypothesis`를 분리한다.

---

# Per-Video Analysis Template

## Identity
- URL:
- Title:
- Duration:
- Topic class:
- Episode grammar candidate:

## Core Promise
- Surface subject:
- Hidden question:
- Final payoff:

## Timeline

| Time | Narration/Beat | Claim | Visual action | Camera | Spatial state | Evidence role | Note |
|---|---|---|---|---|---|---|---|

## Hook Analysis
- first visual contradiction:
- question lock time:
- first transformation time:
- first major payoff time:

## Visual Grammar Counts
- cutaway:
- transparency:
- explode:
- flow visualization:
- map/scale transition:
- inside flythrough:
- reconstruction:
- reassembly:

숫자 자체가 목표는 아니다. 비교용 fingerprint로 쓴다.

## Continuity Observations
- Hero Object consistency:
- orientation consistency:
- likely geometry-backed scenes:
- likely generative scenes:
- uncertain:

## Script DNA
- sentence length tendency:
- explanation depth:
- use of analogy:
- use of rhetorical questions:
- amount of historical context:
- transition style:

## What to Learn
- reusable principle:

## What NOT to Copy
- distinctive phrasing:
- distinctive shot sequence:
- branding/style elements:

---

# Cross-Video Synthesis

10편 분석 후 세 그룹으로 분리한다.

## Channel Constants
여러 주제에서 반복되는 핵심 DNA.

## Episode-Type Rules
특정 소재/문법에서만 반복되는 규칙.

## One-Off Flourishes
한 편에서만 나온 연출. 이를 일반 규칙으로 승격하지 않는다.

---

# Output Artifacts

Benchmark가 끝나면 최소 다음이 나온다.

1. `reference-index`
2. 10 × per-video timeline analysis
3. Script DNA summary
4. Visual action taxonomy revision
5. Camera grammar revision
6. Hook/payoff pattern map
7. Reference anti-copy list
8. Harness implications

---

# Harness Implications Extraction

레퍼런스 분석의 마지막에는 반드시 다음 질문에 답한다.

- 어떤 분석은 독립 specialist가 필요한가?
- 어떤 artifact가 handoff에서 반드시 살아남아야 하는가?
- 어떤 오류가 다음 단계에서 복구 불가능한가?
- 어디서 사람 검수가 가장 값싼가?
- 어떤 memory가 episode를 넘어 재사용되는가?

이 답이 Harness Architecture를 검증/수정한다.

---

# Completion Gate

“영상 10개를 봤다”는 완료가 아니다.

완료 조건:
- transcript와 frames가 함께 분석됨
- timestamp alignment가 있음
- 반복 규칙과 예외가 분리됨
- observable fact와 tool hypothesis가 분리됨
- 우리 Script/Visual Grammar에 반영된 변경점이 있음
- 하네스에 미치는 영향이 기록됨

실제 benchmark corpus의 수집/분석은 구현 코드가 아니라 **리서치 작업**이므로 필요 시 Phase 0 이후에도 코딩 없이 수행 가능하다. 다만 자동 분석 도구 구현은 사용자 승인 전 금지한다.

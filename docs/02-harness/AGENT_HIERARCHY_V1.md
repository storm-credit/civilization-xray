# Civilization X-Ray — Agent Hierarchy v1

Status: **Design-only / no implementation code**

## Executive Decision

Civilization X-Ray의 제작 에이전트 계층은 다음처럼 구성한다.

```text
USER / HUMAN EXECUTIVE
        │
        ▼
┌──────────────────────────┐
│ PROJECT ORCHESTRATOR     │
│ project state / gates    │
│ budget / priority        │
│ retry / escalation       │
└────────────┬─────────────┘
             │
      episode production order
             │
             ▼
┌──────────────────────────┐
│ VIDEO DIRECTOR           │
│ visual storytelling      │
│ shot routing / continuity│
│ camera / transition plan │
└──────┬──────────┬────────┘
       │          │
       ▼          ▼
┌─────────────┐  ┌──────────────────┐
│ BLENDER     │  │ VEO CINEMATIC    │
│ SPECIALIST  │  │ CAMERA SPECIALIST│
│ spatial truth│ │ generative cinema│
└──────┬──────┘  └────────┬─────────┘
       │                  │
       └─────────┬────────┘
                 ▼
        production candidates
                 │
                 ▼
┌──────────────────────────┐
│ INDEPENDENT VISUAL QA    │
│ continuity / truth / sync│
└────────────┬─────────────┘
             │ pass / reject
             ▼
       VIDEO DIRECTOR
             │
             ▼
      PROJECT ORCHESTRATOR
```

Optional logical capability under Video Director:
- 2D Motion / Compositing Specialist

초기에는 독립 물리 agent가 아닐 수 있지만, 지도·도식·라벨·합성 책임은 Blender/Veo 책임과 분리한다.

---

# 1. Design Principle

이 계층은 “모델별 에이전트를 많이 만든다”가 목적이 아니다.

목적:
1. 프로젝트 판단과 영상 판단을 분리한다.
2. deterministic spatial truth와 generative cinematic freedom을 분리한다.
3. Director가 두 제작 방식을 장면 목적에 따라 선택한다.
4. 제작자가 자기 결과를 최종 승인하지 못하게 한다.
5. 각 handoff를 artifact로 남겨 긴 롱폼에서도 상태가 유실되지 않게 한다.

---

# 2. Authority Boundaries

## Project Orchestrator Authority
Owns:
- episode lifecycle state
- gate transition
- priority
- cost/budget ceiling
- retry ceiling
- human approval state
- escalation
- artifact version authority

Does NOT own:
- 카메라 미학 세부 결정
- Blender mesh 세부 구현
- Veo prompt 세부 표현
- factual claim 자체의 truth verdict

## Video Director Authority
Owns:
- 영상 전체 시각적 해석
- shot sequence
- shot medium routing
- camera language
- transition grammar
- pacing through visuals
- Blender ↔ Veo ↔ 2D 연결
- final visual assembly intent

Cannot override:
- verified claims
- Spatial / Asset Bible hard locks
- reconstruction level
- rights/provenance restrictions
- project budget gate without escalation

## Blender Specialist Authority
Owns deterministic spatial shots.

If topology/location/orientation itself is explanatory evidence, Blender Specialist has technical veto over a generative-only solution.

## Veo Cinematic Camera Specialist Authority
Owns generative cinematic shots.

It may propose camera framing, lens intent, movement, first/last frame constraints and reference-image strategy, but cannot claim deterministic geometric continuity that the generation model cannot guarantee.

## Independent Visual QA Authority
May reject any shot/sequence even if Video Director approved it.

Final QA must remain logically independent from the creator of the asset.

---

# 3. Routing Rule

Every shot receives one primary route:

- `BLENDER_DETERMINISTIC`
- `VEO_GENERATIVE`
- `TWO_D_MOTION`
- `STILL_COMPOSITE`
- `HYBRID`

### Blender-first signals
Use Blender when:
- component position is evidence
- exact section/cutaway matters
- camera path teaches spatial relation
- same structure must survive multiple angles
- explode/reassemble is required
- flow must follow topology

### Veo-first signals
Use Veo when:
- historical human activity is the subject
- atmosphere / crowd / weather / water behavior dominates
- cinematic emotion is more important than exact topology
- shot is an establishing or cinematic bridge
- a controlled start/end-frame generative transition is useful

### Hybrid signals
Use Hybrid when:
- factual geometry must remain fixed but the scene needs cinematic life
- Blender render can serve as first/last/reference frame
- generated human/weather/action layers must be composited around a locked structure

---

# 4. Required Handoff Artifacts

## Project Orchestrator → Video Director
`Episode Production Order`
- approved Story Pack version
- approved Visual Plan version
- Spatial / Asset Bible version
- budget ceiling
- approved reconstruction boundaries
- required human gates
- stop conditions

## Video Director → Specialists
`Shot Work Order`
- shot id
- explanatory objective
- linked narration unit
- linked claim ids
- route
- start state
- end state
- camera intent
- duration
- continuity locks
- transition in/out
- success criteria
- fallback route

## Specialist → Video Director
`Shot Candidate Package`
- output reference
- method/model/tool version
- prompt/scene spec version
- camera result metadata
- deviations from work order
- known limitations
- recommended next action

## Video Director → Visual QA
`Sequence Review Package`
- ordered shots
- narration sync
- transition map
- visual continuity anchors
- reconstruction labels
- known compromises

## Visual QA → Director / Orchestrator
`QA Verdict`
- PASS / REVISE / REJECT / ESCALATE
- failed criteria
- rollback target
- required correction

---

# 5. Retry Ownership

### Blender failure
Examples:
- wrong axis
- camera collision
- incorrect section
- geometry mismatch

Retry owner: Blender Specialist.

Escalate to Video Director when shot objective itself is incompatible with the Spatial Bible.

### Veo failure
Examples:
- object drift
- unwanted camera move
- transition misses last frame
- character/action inconsistency

Retry owner: Veo Specialist.

Retry must change a causal input: prompt, reference, first/last frame, route, shot length or composition. Blind identical retries are prohibited.

Escalate to Video Director when repeated generative failure suggests Blender/2D/Hybrid is the correct route.

### Sequence failure
Examples:
- individually good shots but confusing order
- orientation breaks between media
- explanation does not match narration

Owner: Video Director.

### Budget/system failure
Owner: Project Orchestrator.

---

# 6. Stop / Escalation Conditions

Specialists must stop rather than improvise when:
- hard-lock geometry is missing or contradictory
- claim does not support requested visual certainty
- reconstruction level is undefined
- the requested generative shot would present speculation as fact
- repeated attempts exceed stage retry ceiling
- required paid capability exceeds approved budget
- source/license status blocks commercial use

---

# 7. Physical Agent Count

This document defines **logical production roles**, not a permanent process count.

Minimum initial physical arrangement may be:
1. Project Orchestrator
2. Video Director
3. Blender Specialist
4. Veo Cinematic Camera Specialist
5. Visual QA

2D/compositing may initially be a Video Director capability and split later when workload justifies it.

Research, claim verification and narrative roles remain upstream capabilities defined in the broader harness. They are not replaced by this production hierarchy.

---

# 8. Success Criteria

The hierarchy passes when:
- a shot always has exactly one accountable route owner
- Blender and Veo responsibilities do not overlap ambiguously
- Project Orchestrator does not become a giant creative super-agent
- Video Director can replace a failed medium without rewriting the episode architecture
- QA can independently reject creator output
- every retry has a documented cause and changed input
- factual/spatial locks survive all handoffs
- no paid camera platform is a mandatory dependency

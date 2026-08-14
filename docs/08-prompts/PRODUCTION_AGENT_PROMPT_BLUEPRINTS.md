# Production Agent Prompt Blueprints

Status: **Design templates — not runtime implementation**

이 문서는 Project Orchestrator / Video Director / Blender Specialist / Veo Cinematic Camera Specialist / Visual QA가 실제 실행환경에서 사용할 prompt contract를 정의한다.

공통 메타 프롬프팅 순서:

`Context Dump → Missing Context Check → Constraint Lock → Output Contract → Success Criteria → Stop Conditions → Self-Review`

---

# 1. Shared Prompt Envelope

모든 production agent 실행은 최소 다음 필드를 가진다.

## Role
- agent role
- authority boundary
- what this role must never decide

## Goal
- one execution goal
- expected artifact/output

## Context Dump
- episode id
- current stage
- relevant artifact ids + versions
- linked claim/narration ids
- project rules excerpt
- known prior failures

## Constraints
- hard locks
- budget/retry ceiling
- reconstruction level
- rights/provenance constraints
- tool/model constraints

## Output Contract
- required fields
- verdict/state
- deviations
- next owner

## Success Criteria
- measurable pass conditions

## Stop Conditions
- when to stop and escalate instead of guessing

## Self-Review
- contradiction scan
- placeholder/TBD scan
- unsupported certainty scan
- scope creep scan

---

# 2. Project Orchestrator Prompt Blueprint

## Goal
Advance one episode by exactly one justified orchestration decision.

## Required Context
- current Episode Run Ledger
- gate state
- artifact registry summary
- outstanding blockers
- budget state
- human approval state

## Must Produce
1. current state
2. missing prerequisites
3. next owner
4. work order id
5. required inputs
6. success criteria
7. retry/escalation ceiling
8. next gate

## Stop
- contradictory gate verdicts
- missing canonical artifact version
- budget/human decision required

---

# 3. Video Director Prompt Blueprint

## Goal
Convert approved story/visual artifacts into a coherent shot plan and route each shot to the right medium.

## Required Context
- Story Pack
- Visual Plan
- Spatial / Asset Bible
- channel visual DNA
- camera/transition grammar

## Must Produce Per Shot
- shot id
- narrative purpose
- explanatory objective
- route: Blender / Veo / 2D / Still / Hybrid
- camera intent
- start/end state
- continuity anchor
- transition in/out
- duration intent
- linked claims
- fallback route

## Stop
- hard geometry contradiction
- unsupported reconstruction
- missing explanatory objective

---

# 4. Blender Specialist Prompt Blueprint

## Goal
Design a reproducible deterministic scene/camera solution for one approved shot.

## Required Context
- Shot Work Order
- Spatial / Asset Bible relevant subset
- dimensions/ratios/axes
- reconstruction level
- camera rig options

## Must Produce
- component/geometry decomposition
- coordinate/orientation plan
- fidelity grade
- camera rig + target
- section/explode/transparency states
- render layers
- reusable asset opportunities
- deviations/unknowns

## Success
- hard locks preserved
- shot can be regenerated from spec
- camera teaches the intended relation
- no invented precision

## Stop
- conflicting dimensions
- unsupported interior topology
- manual modeling escalation likely cheaper/safer

---

# 5. Veo Cinematic Camera Specialist Prompt Blueprint

## Goal
Design one generative cinematic shot without corrupting factual/spatial truth.

## Required Context
- Shot Work Order
- Video Director intent
- approved first frame/reference images
- optional last frame
- immutable visual constraints
- reconstruction level

## Must Produce
- subject
- action
- environment
- style
- camera position/movement
- composition
- lens/focus intent
- ambiance
- first/last-frame strategy
- reference-image strategy
- invariants
- forbidden mutations
- retry mutation plan

## Success
- intended cinematic function achieved
- hard factual structure not presented falsely
- entry/exit state usable by neighboring shots
- prompt/version/references reproducible enough for manifest

## Stop
- deterministic geometry is required
- repeated drift after causal retries
- speculation would look factual

---

# 6. Visual QA Prompt Blueprint

## Goal
Independently determine whether the sequence is safe and clear enough to pass.

## Required Context
- Sequence Review Package
- relevant Story Pack / Visual Plan
- Spatial / Asset Bible locks
- reconstruction/scale metadata
- creator manifests

## Must Produce
- PASS / REVISE / REJECT / ESCALATE
- evidence for verdict
- failures by category
- exact rollback target
- required correction

## Review Categories
- object continuity
- spatial continuity
- semantic continuity
- temporal continuity
- script↔visual alignment
- visual truth/reconstruction
- generative artifacts
- orientation/camera readability

## Forbidden
- vague “looks good” pass
- using creator rationale as sole evidence
- hiding uncertainty to keep schedule

---

# 7. Prompt Versioning

Every production prompt run must eventually record:
- role
- prompt template version
- context artifact versions
- model/tool version
- result artifact id/version
- retry number
- change from previous retry

Exact storage/runtime implementation is deferred.

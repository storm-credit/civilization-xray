# Core Artifact Contracts v1

Status: **Design Closure 0.6 / no-code contract**

Purpose: Validation 0.5에서 선택한 7개 물리 Core Artifact가 실제 한 편의 episode를 끝까지 운반할 수 있도록 최소 필드, version/stale 규칙, gate 증거를 고정한다.

원칙:
- logical role과 physical file을 혼동하지 않는다.
- 각 artifact는 다음 단계가 재해석 없이 사용할 만큼만 명시한다.
- 필드가 많다는 이유로 품질이 보장되지는 않는다.
- `status=PASS` 문자열만으로 gate를 통과하지 않는다. 필수 evidence/artifact/version이 실제로 존재해야 한다.
- 구현 데이터 포맷(JSON/YAML/DB)은 아직 정하지 않는다.

---

## 0. Universal Header

모든 episode core artifact는 최소 다음 메타데이터를 갖는다.

- `episode_id`
- `artifact_type`
- `version`
- `status`: DRAFT | REVIEW | LOCKED | STALE | SUPERSEDED | REJECTED
- `created_by_role`
- `source_artifact_versions[]`
- `created_at / reviewed_at` 개념
- `supersedes`
- `hard_dependencies[]`
- `known_assumptions[]`
- `open_questions[]`
- `gate_evidence[]`

`LOCKED`는 절대 불변이라는 뜻이 아니라 downstream 제작의 기준 버전이라는 뜻이다. upstream truth가 바뀌면 새 version을 만들고 영향받는 downstream을 `STALE` 처리한다.

---

# P1. Episode Brief

## Mission
에피소드가 무엇을 묻고, 무엇을 설명하며, 무엇을 설명하지 않는지를 잠근다.

## Required fields
- `working_title`
- `central_question`
- `viewer_promise`
- `episode_grammar`: MYSTERY | JOURNEY | BUILD | FAILURE | HYBRID
- `target_audience`
- `xray_value`
- `explanatory_unit`: object | system | component | representative_section
- `case_anchor`
- `scope_in[]`
- `scope_out[]`
- `candidate_misconception`
- `topic_score`
- `early_fact_risks[]`
- `production_risks[]`
- `success_criteria[]`

## Gate
Topic Gate PASS requires:
- one clear central question
- visually provable mechanism
- explicit scope exclusion
- case anchor if a real named case carries the proof
- no known fatal evidence gap

---

# P2. Evidence Pack

## Mission
Source → Claim → Uncertainty를 한 artifact에서 보존한다.

## Source record
- `source_id`
- bibliographic identity / DOI / institutional publisher
- source class: PRIMARY/INSTITUTIONAL | PEER_REVIEWED | SECONDARY | CONTEXT_ONLY
- scope
- date
- access/review date
- relevant finding summary
- rights note for figures/media

## Claim row
- `claim_id`
- `claim_text`
- `source_ids[]`
- `status`: VERIFIED | SCOPE_LIMITED | DISPUTED | UNSUPPORTED | OPEN
- `confidence`
- `scope_qualifier`
- `contradicts_or_limits[]`
- `visual_implication`
- `narration_allowed_form`
- `forbidden_overclaim`

## Conflict map
서로 다른 자료가 다른 foundation typology/수치/시기/해석을 말하면 하나를 조용히 선택하지 않는다.

- conflict id
- positions
- source ids
- likely reason: site/era/method/scope difference
- episode treatment

## Gate
Research Gate PASS requires:
- central mechanism claims have source IDs
- scope-limited claims carry qualifier
- central unresolved conflict has an editorial treatment
- visuals cannot imply higher certainty than evidence

---

# P3. Story Pack

## Mission
Claim을 시청 가능한 정보 순서와 narration units로 변환한다.

## Beat row
- `beat_id`
- function
- viewer question at entry
- information revealed
- linked claim ids
- emotional/attention state
- planned duration band
- exit question / handoff

## Narration unit
- `unit_id`
- `beat_id`
- `sentence_class`: CLAIM | EXPLANATION | ORIENTATION | SCALE | TRANSITION | DRAMA | QUALIFIER | PAYOFF
- `narration_draft`
- `claim_ids[]`
- `certainty_language`
- `visual_dependency`
- `duration_intent`

## Gate
Script Gate PASS requires:
- cold open promise and final payoff match
- no narration claim exceeds Evidence Pack
- each central explanation has a visual dependency
- qualifier is not removable without changing truth
- no encyclopedia detour that does not advance central mechanism

---

# P4. Visual Plan

## Mission
Narration unit를 실제 explanatory shot/work order로 바꾼다.

## Visual unit / shot row
- `shot_id`
- `linked_unit_ids[]`
- `claim_ids[]`
- `visual_objective`
- `proof_question`: 화면이 무엇을 증명해야 하는가?
- `visual_action[]`
- `medium_route`: BLENDER | VEO | 2D | STILL | REAL_REFERENCE | HYBRID
- `subject_component_ids[]`
- `camera_rig`
- `camera_start_state`
- `camera_end_state`
- `orientation_anchor`
- `entry_state`
- `exit_state`
- `transition_in`
- `transition_out`
- `continuity_class[]`: OBJECT | SPATIAL | SEMANTIC | TEMPORAL
- `reconstruction_level`: R0 | R1 | R2 | R3
- `scale_treatment`: TRUE_SCALE | SCHEMATIC | EXAGGERATED_FOR_EXPLANATION
- `hard_locks[]`
- `allowed_variation[]`
- `duration_intent`
- `fallback_visual`
- `risk_level`

## Routing rule
매 shot은 미학보다 먼저 다음 순서로 판단한다.
1. 무엇을 증명해야 하는가?
2. topology/position/scale가 증거인가?
3. viewer orientation을 유지해야 하는가?
4. 사람/날씨/분위기 생성이 핵심인가?
5. 더 싼 2D/still이 더 명확한가?

## Gate
Visual Map/Previs Gate PASS requires:
- central mechanism의 모든 핵심 문장에 explanatory visual coverage
- decorative B-roll만으로 central claim을 대체하지 않음
- high-risk geometry shot은 Spatial Bible lock을 참조
- expensive production 전에 entry/exit state와 fallback 존재

---

# P5. Spatial / Asset Bible

## Mission
많은 shot이 공유하는 공간/구조의 정본을 제공한다.

## Required fields
- `hero_scope`
- `case_anchor`
- `canonical_section`
- `coordinate/orientation_convention`
- `component_registry[]`
- `component_relationships[]`
- `hard_locks[]`
- `soft_locks[]`
- `free_fields[]`
- `semantic_anchors[]`
- `unknown_or_reconstructed_zones[]`
- `scale_policy`
- `asset_acquisition_route`
- `reference_bindings[]`

## Hard lock examples
- bearing wall ↔ pile field relative position
- section direction
- waterline/ground relationship
- load path order

## Gate
Spatial Readiness PASS requires:
- unresolved geometry contradiction 없음
- representative reconstruction이면 명시됨
- unknown zone을 AI가 채워 사실처럼 보이게 하지 않음
- repeated shots가 동일 component IDs를 참조 가능

---

# P6. Production Pack

## Mission
Previs/generation/render/edit inputs와 생성 결과의 desired/selected state를 관리한다.

## Production item
- `production_item_id`
- `shot_id`
- `shot_spec_version`
- `provider/tool capability`
- `model/version` when generated
- `prompt_artifact_id/hash`
- `reference_binding_ids[]`
- `input_asset_versions[]`
- `attempts[]`
- `output_asset_id/path concept`
- `normalization_status`
- `cost_estimate / cost_actual concept`
- `selected_status`: UNREVIEWED | SELECTED | REJECTED | STALE
- `qa_verdict_ref`

## Continuity Bridge when relevant
- `previous_end_state`
- `intended_start_state`
- `intended_end_state`
- `next_start_target`
- `compatibility_note`
- `continuity_risk`

## Gate
Production item cannot be SELECTED if:
- source Shot Spec version is stale
- hard reference binding changed
- output failed Visual QA
- provider/model/prompt provenance is missing for generated media

---

# P7. Review & Run Ledger

## Mission
“무슨 일이 왜 일어났는가?”를 복원한다.

## Event types
- stage transition
- artifact lock
- QA verdict
- human approval
- retry
- reroute
- budget hold
- stale propagation
- deviation
- rights block
- release decision

## Event fields
- `event_id`
- timestamp concept
- actor role
- input artifact versions
- action
- outcome
- evidence
- causal reason
- affected downstream artifacts
- rollback/escalation target

## Gate
완료 주장은 Ledger에서 다음을 재구성할 수 있어야 한다.
- 어떤 artifact version이 승인되었는가?
- 어떤 claim/source가 central explanation을 지지하는가?
- 어떤 shot이 어떤 spec으로 제작되었는가?
- 실패/재시도 이유는 무엇인가?
- 어떤 downstream이 stale 되었고 어떻게 복구되었는가?

---

# Dependency / Stale Propagation Matrix

## Episode Brief scope change
Invalidate/review:
- Evidence Pack
- Story Pack
- Visual Plan
- Spatial Bible if explanatory unit/case anchor changed
- all downstream production

## Evidence Pack central claim change
Invalidate/review:
- linked Story units
- linked Visual shots
- affected Spatial locks
- selected Production items
- narration/TTS/captions
- title/thumbnail claim

## Story Pack wording-only change
If meaning unchanged:
- voice timing
- captions
- edit timing review
- music cue timing review
Visual geometry may remain valid.

If meaning/claim changes:
- linked Visual/Spatial/Production become STALE.

## Spatial Bible hard-lock change
Invalidate:
- all shots depending on changed component/axis
- Blender renders
- Veo shots using those frames as geometry anchors
- continuity bridges
- downstream edit segments

## Visual Plan camera-only change
Invalidate:
- affected production item and transition neighbors
- not necessarily Story/Evidence

## Picture timing change
Review:
- voice if edit changes meaning/pause
- music cue in/out
- SFX sync
- captions

---

# Executable Gate Principle for Phase 1

향후 구현 시 gate executor는 상태 문자열뿐 아니라 실제 artifact integrity를 검사해야 한다.

Conceptual checks:
- referenced artifact exists
- expected version matches
- required fields parse
- required source/prompt/ref IDs resolve
- selected media exists and is non-empty
- stale dependency 없음
- hard-fail verdict 없음

이 원칙은 OddEngine에서 확인한 executable artifact gate 패턴을 Civilization X-Ray의 7-artifact blackboard에 맞게 최소화한 것이다.

---

# Design Closure Verdict

7개 core artifact는 이 contract 수준이면 한 편을 시작부터 release까지 운반할 수 있다.
추가 physical artifact는 complexity trigger가 실제로 발생할 때만 만든다.

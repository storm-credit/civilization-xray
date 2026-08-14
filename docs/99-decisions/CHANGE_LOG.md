# Change & Deviation Log

계획이 바뀌거나 처음 가정과 다른 결과가 나왔을 때 반드시 기록한다.

## Template

### YYYY-MM-DD — Decision title

- Previous decision / assumption:
- New decision:
- Trigger / evidence:
- Why changed:
- Impact:
- Reversible?:
- Rollback path:
- Affected stages/files:
- Follow-up validation:

---

## 2026-08-14 — Repository initialized

- Previous decision / assumption: 새 AI 롱폼 콘텐츠 프로젝트를 별도 저장소로 구성한다.
- New decision: 프로젝트 저장소명을 `civilization-xray`로 확정.
- Trigger / evidence: 건축만이 아니라 도시·역사·인프라까지 포괄하면서도 “내부 원리를 해부한다”는 정체성을 유지하기 위해 선택.
- Why changed: 해당 없음. 초기 결정.
- Impact: 프로젝트 문서/브랜드 코드네임 전체.
- Reversible?: Yes.
- Rollback path: 저장소 rename 및 문서 일괄 수정.
- Affected stages/files: all design docs.
- Follow-up validation: 사용자 인터뷰에서 content center of gravity를 확인.

## 2026-08-14 — Harness must follow completed discovery

- Previous decision / assumption: 멀티에이전트/하네스가 필요할 가능성이 높다.
- New decision: 에이전트 수나 topology를 미리 고정하지 않고, 브레인스토밍·맹점 훑기·pre-mortem·성공조건이 충분히 정리된 뒤 Harness Readiness Gate를 통과해야만 하네스 구조를 확정한다.
- Trigger / evidence: 사용자가 “충분히 브레인스토밍과 맹점 훑기가 완성되면 그에 맞는 하네스 구조를 잡는 것이 중요하다”고 명시.
- Why changed: 도메인을 하네스에 끼워 맞추는 premature architecture를 방지하기 위해.
- Impact: Phase 0 workflow, CLAUDE.md, Discovery Gates, Harness Design Policy.
- Reversible?: Yes, but changing requires explicit rationale.
- Rollback path: Harness Readiness Gate 수정 + CLAUDE.md 동기화.
- Affected stages/files: `CLAUDE.md`, `docs/01-discovery/DISCOVERY_GATES.md`, `docs/02-harness/HARNESS_DESIGN_POLICY.md`.
- Follow-up validation: 대표 episode/visual grammar 분석 후 실제 책임 경계가 드러나는지 검증.

## 2026-08-14 — Phase 1 physical artifacts simplified from 12 to 7

- Previous decision / assumption: 12 logical artifact types could become the default episode-level physical artifact set.
- New decision: Keep logical distinctions but use 7 default physical core artifacts for Phase 1: Episode Brief, Evidence Pack, Story Pack, Visual Plan, Spatial/Asset Bible, Production Pack, Review & Run Ledger.
- Trigger / evidence: Three paper walkthroughs showed that some artifacts are tightly coupled and separate files would add synchronization/context overhead without adding control.
- Why changed: Reduce harness complexity while preserving provenance and gate boundaries.
- Impact: Future Phase 1 artifact schema, context packets, blackboard registry.
- Reversible?: Yes.
- Rollback path: Split any combined artifact when complexity triggers are met.
- Affected stages/files: `docs/09-validation/ARTIFACT_PRUNING_REVIEW.md`, future implementation plan.
- Follow-up validation: Use one real episode to measure artifact size and reviewer handoff burden.

## 2026-08-14 — Hero Object model expanded to Spatial / Asset Bible

- Previous decision / assumption: A single Hero Object Bible could represent the canonical visual subject of an episode.
- New decision: Use Spatial / Asset Bible supporting `object | system | component` scope.
- Trigger / evidence: Roman aqueduct and undersea tunnel walkthroughs require route/system continuity rather than one object only.
- Why changed: Prevent object-centric design from distorting infrastructure/system episodes.
- Impact: Asset architecture, continuity QA, visual planning.
- Reversible?: No strong reason to revert; object is now a supported subtype.
- Rollback path: Not needed; use hero_scope=object for object-centric episodes.
- Affected stages/files: `docs/09-validation/PAPER_WALKTHROUGHS.md`, `docs/09-validation/VALIDATION_0_5_FINAL.md`.
- Follow-up validation: Apply to a city-scale hidden-system episode.

## 2026-08-14 — Continuity expanded beyond geometry

- Previous decision / assumption: Continuity was primarily Hero Object geometry/orientation consistency.
- New decision: Track four classes: object, spatial, semantic-journey, temporal continuity.
- Trigger / evidence: System Journey episodes can maintain correct geometry yet lose the viewer's sense of following the same water/force/process across map, diagram and 3D views.
- Why changed: Viewer comprehension requires semantic continuity as well as geometric consistency.
- Impact: QA rubric, Visual Plan, Spatial/Asset Bible.
- Reversible?: Yes, but simplification would reduce explanatory coverage.
- Rollback path: Collapse classes only if pilot evidence shows no value.
- Affected stages/files: `docs/09-validation/PAPER_WALKTHROUGHS.md`, `docs/09-validation/VALIDATION_0_5_FINAL.md`.
- Follow-up validation: Check semantic anchor use in an aqueduct/water episode.

## 2026-08-14 — 2D diagrams promoted to first-class visual capability

- Previous decision / assumption: 3D/generative visual methods were the dominant explanatory options, with diagrams treated implicitly as overlays/fallbacks.
- New decision: Technical diagrams, map/elevation animation and motion graphics are first-class capabilities selected by explanatory objective.
- Trigger / evidence: Tunnel alignment and aqueduct walkthroughs showed that tiny angle errors, elevation profiles and routes may be clearer in 2D before 3D.
- Why changed: Avoid forcing every concept into expensive or less-clear 3D.
- Impact: Capability registry, Visual Plan, cost model.
- Reversible?: Yes.
- Rollback path: None needed; 3D remains available when superior.
- Affected stages/files: `docs/09-validation/VALIDATION_0_5_FINAL.md`.
- Follow-up validation: Compare 2D-first vs 3D-first explanation in a pilot.

## 2026-08-14 — Scale treatment becomes explicit visual-truth metadata

- Previous decision / assumption: Reconstruction levels covered visual truth, while scale exaggeration was handled informally.
- New decision: Every relevant engineering visual can declare TRUE_SCALE / SCHEMATIC / EXAGGERATED_FOR_EXPLANATION.
- Trigger / evidence: Slopes, angles and layers can be physically correct but visually unreadable at true scale.
- Why changed: Allow explanatory exaggeration without fake precision.
- Impact: Visual Plan, QA, narration/labeling rules.
- Reversible?: Yes.
- Rollback path: Remove only if no engineering visuals require scale transformation.
- Affected stages/files: `docs/09-validation/PAPER_WALKTHROUGHS.md`, `docs/09-validation/VALIDATION_0_5_FINAL.md`.
- Follow-up validation: Test with elevation/angle examples.

## 2026-08-14 — Blender-first modeling and deterministic camera backbone

- Previous decision / assumption: Production design distinguished geometry-backed vs generative visuals but did not specify how models and camera motion would actually be acquired without a dedicated modeler.
- New decision: Use a four-path Model Acquisition Router: M0 no-3D/2D, M1 procedural-parametric Blender geometry as default, M2 approved existing assets, M3 verified AI image-to-3D seed, M4 human modeler as exception. Deterministic explanatory camera moves use a planned reusable Blender camera-rig vocabulary. Higgsfield is not a mandatory dependency.
- Trigger / evidence: User identified paid Higgsfield cost and uncertainty about who would create 3D models. Blender supports programmatic animation, while current AI 3D tools can provide candidate meshes but require accuracy/license review.
- Why changed: Remove the hidden assumption that a full-time 3D artist is required and make camera/model production routable by explanatory need.
- Impact: Visual system, Production Pack, Spatial/Asset Bible, future model/tool registry, cost model.
- Reversible?: Yes.
- Rollback path: Promote human modeling or another deterministic DCC path if pilot evidence shows procedural Blender is insufficient.
- Affected stages/files: `docs/05-visual/MODELING_CAMERA_RENDER_ROUTER.md`, future Phase 1 planning.
- Follow-up validation: Compare procedural/existing/AI/human paths on aqueduct, Venetian foundation and ornate cathedral asset classes before implementation lock.

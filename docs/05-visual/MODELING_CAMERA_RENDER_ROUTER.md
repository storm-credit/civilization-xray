# Modeling, Camera & Render Router

Status: **Design decision — no implementation code**

## Executive Decision

Civilization X-Ray는 Phase 1에서 상시 인간 3D 모델러를 기본 전제로 두지 않는다.

기본 제작 구조는 다음과 같다.

> **Blender = spatial truth / deterministic camera / reusable geometry backbone**  
> **Generative cinematic video = reconstruction / atmosphere / human activity, via direct provider or supervised workbench**  
> **2D motion graphics = diagrams / maps / abstract mechanisms**  
> **Human modeler = exception path only**

Google video models remain direct-provider candidates behind a capability adapter. AniJam is an optional supervised workbench candidate under the same Generative Cinematic Video responsibility; it is not a new director, agent, orchestra or spatial authority.

Higgsfield는 필수 dependency에서 제외한다. 비용 또는 특정 연출 이점이 명확해질 때만 optional adapter로 검토한다.

---

# 1. Why a Human Modeler Is Not the Default

Civilization X-Ray의 핵심 3D는 게임/영화용 캐릭터 sculpt가 아니라 대부분 다음과 같다.

- walls
- slabs
- columns
- arches
- pipes
- tunnels
- foundations
- piles
- chambers
- bridges
- terrain sections
- roads
- canals
- structural frames
- simple machines

이들은 예술적 sculpt보다 **dimension / ratio / topology / axis / connection**이 중요하다.

따라서 먼저 연구 산출물에서 구조 관계를 확정하고, Blender의 primitive / curve / modifier / geometry 기반 접근으로 만드는 편이 설명 정확도와 재사용성에 유리하다.

사람 모델러는 “모양을 예쁘게 만드는 사람”이 아니라 자동/절차 경로가 설명 품질을 만족하지 못할 때 투입하는 specialist로 정의한다.

---

# 2. Model Acquisition Router

각 asset은 아래 경로 중 가장 싼 경로에서 시작하며, 품질 gate 실패 시에만 다음 단계로 승격한다.

## M0 — No 3D

Use when:
- elevation profile
- map route
- timeline
- force diagram
- simple section
- abstract system

Method:
- 2D diagram
- motion graphics
- vector/map animation

Rule:
3D가 정보량을 늘리지 않으면 모델링하지 않는다.

---

## M1 — Procedural / Parametric Blender Geometry — DEFAULT

Use when:
- 구조가 primitive 조합으로 설명 가능
- 정확한 비율/축/경로가 중요
- 여러 camera angle에서 같은 구조를 유지해야 함
- cutaway / explode / transparency / flow animation 필요

Inputs from Spatial / Asset Bible:
- dimensions or relative ratios
- coordinate origin
- primary axes
- component list
- component relationships
- hard locks
- section planes
- uncertainty zones

Typical asset examples:
- Roman aqueduct
- Venetian pile foundation system
- pyramid chamber/shaft diagram
- tunnel cross section
- bridge structural frame
- flood channel
- subway station section

Phase 1 intent:
AI/agent may eventually translate approved structured asset specifications into Blender operations, but that automation is **not implemented during design phase**.

---

## M2 — Approved Existing Asset

Use when:
- generic environment/prop exists
- exact geometry is not explanatory evidence
- building exterior is background/context
- reuse is cheaper than construction

Requirements:
- source recorded
- license recorded
- allowed commercial use confirmed before publication
- asset cannot silently override Spatial Bible hard locks

Examples:
- generic trees
- rocks
- furniture
- crowd props
- generic historical objects not central to the explanation

---

## M3 — AI Image-to-3D / Reconstruction Seed

Use when:
- fast proxy is needed
- organic/ornamental shape is expensive procedurally
- reference images exist
- generated geometry can be verified and corrected before use

Rules:
- AI-generated mesh is **not factual authority**.
- Never infer historical/engineering truth from generated mesh.
- Hard-lock geometry must be checked against sources.
- Use first as proxy or surface-detail source unless it passes geometry QA.
- Tool/model/dependency license must be reviewed before commercial publication.

Candidate technology research:
- Microsoft TRELLIS / TRELLIS.2 image-to-3D can export mesh/GLB candidates.
- Tencent Hunyuan3D family exposes image-to-shape pipelines and Blender integration paths.

These are capability references, not locked production dependencies.

---

## M4 — Human Modeler / Contractor — EXCEPTION

Escalate when one or more are true:
- important object has complex non-parametric geometry
- close-up ornate surface detail is essential
- archaeological reconstruction requires deliberate expert interpretation
- asset will be reused across many episodes and deserves production-quality master asset
- M1/M2/M3 repeatedly fail continuity/quality gates
- cleanup cost of generated mesh exceeds manual creation cost

Preferred staffing model:
- per-asset or per-episode contractor
- not full-time modeler during initial validation season

Deliverable must follow the same Spatial / Asset Bible and source/provenance rules as automated assets.

---

# 3. Asset Fidelity Grades

Do not demand final-film quality from every model.

## G0 — Blockout
- boxes / cylinders / curves
- proportions only
- used for camera and pacing tests

## G1 — Explanatory
- correct topology and major dimensions
- clean cutaways
- semantic materials
- sufficient for most X-Ray sequences

## G2 — Presentation
- refined silhouette
- better materials
- medium surface detail
- final explanatory close shots

## G3 — Hero / Cinematic
- high detail
- close inspection safe
- expensive

Default target for Civilization X-Ray explanatory shots: **G1–G2**.

G3 requires an explicit value justification.

---

# 4. Camera System

Camera design is not delegated blindly to a generative video model or creative workbench when spatial continuity matters.

## Camera Ownership Rule

If camera motion itself teaches spatial relationship, use deterministic camera control.

If camera motion is mainly cinematic mood, generative video may own the move within the approved Visual Work Order.

A workbench-generated camera plan is never canonical by itself; the Video Director / Visual Plan remains the authority.

---

# 5. Blender Camera Rig Library — Planned

The future harness should expose a small reusable vocabulary rather than invent camera animation from scratch every shot.

## C01 Establish Orbit
Slow orbit around the full asset while keeping subject axis stable.

## C02 Controlled Push-In
Dolly toward a named component or entry point.

## C03 Pull-Out Context Reveal
Detail → structure → city/system context.

## C04 Top-Down Dive
Map/plan view → vertical descent into the system.

## C05 Section Lock
Camera remains perpendicular to a section plane while layers are removed/revealed.

## C06 Interior Spline Flythrough
Camera follows a controlled path through tunnel/channel/chamber.

## C07 Flow Follow
Camera follows water/air/traffic only when orientation remains understandable.

## C08 Exploded Inspection
Camera mostly stable while components separate along defined axes.

## C09 X-Ray Reveal
Exterior view remains registered while shell opacity/removal exposes internals.

## C10 Scale Bridge
Large context → component → micro detail using registered zoom/path rather than unrelated cuts.

## C11 Stress-Test Lockoff
Camera fixed; load/flow/parameter changes.

## C12 Reassembly Return
Reverse spatial operation to prove exploded/cutaway components belong to the original system.

---

# 6. Shot Camera Contract

Future Shot Spec should not merely say “cinematic orbit.”

Minimum camera fields:
- rig_type
- subject / target component id
- start position or semantic position
- end position or semantic position
- look-at target
- lens class / FOV intent
- movement duration
- easing intent
- world axis lock
- section plane if applicable
- orientation anchor
- entry frame state
- exit frame state
- transition_to next shot

Exact numerical schema is deferred to implementation planning.

---

# 7. Transition Grammar

“Transition” is classified by explanatory function, not effect name.

## T1 — Spatial Continuous
Same space, camera continues or match-cuts between known viewpoints.

Best implementation:
- Blender / deterministic 3D

## T2 — Layer Reveal
Surface → transparent → cutaway → internal.

Best implementation:
- Blender material/object state animation
- compositing where needed

## T3 — Scale Transition
City → building → foundation → component.

Best implementation:
- Blender registered camera move
- 2D/3D composite

## T4 — Temporal Reconstruction
Present ruin → historical reconstruction.

Best implementation:
- matched geometry/still as anchor
- generative video or compositing for historical atmosphere

## T5 — Semantic Match
Shape/function match between two different locations or eras.

Best implementation:
- edit/composite; generation optional

## T6 — Cinematic Bridge
Cloud/smoke/water/crowd/light-driven transition where exact geometry is not evidence.

Best implementation:
- generative cinematic video candidate via direct provider or supervised workbench

Rule:
Never use an impressive transition if it causes the viewer to lose spatial orientation during an explanation.

---

# 8. Render / Generation Router

## R-BLENDER — Deterministic Geometry Render

Select when:
- topology is evidence
- exact component location matters
- same asset appears in >= 3 explanatory shots
- cutaway/explode/reassembly is required
- registered camera continuity matters

Output can be final render or compositing layer.

## R-GENERATIVE-VIDEO — Generative Cinematic Layer

Select when:
- historical people/activity
- atmospheric establishing shot
- water/weather/smoke/crowd
- visual reconstruction where exact topology is not presented as evidence
- cinematic bridge

This is a **capability route**, not a permanent vendor/model choice.

### R-GEN-DIRECT — Direct Provider Adapter

Use when:
- automation/programmatic execution matters;
- exact provider/model provenance matters;
- provider-specific controls are required;
- retry/cost/job lifecycle should be machine-observable;
- reproducibility requirements are stronger.

Google video models remain current candidates behind this adapter. Model/version guidance must be refreshed before implementation.

### R-GEN-WORKBENCH — Optional Supervised Creative Workbench

Use when:
- rapid multi-model audition has real value;
- multi-scene character/style consistency is useful;
- historical people/activity/atmosphere spans several shots;
- manual supervision is acceptable;
- reduced app-switching improves production speed.

Current candidate: **AniJam**, validated as `W0 OPTIONAL MANUAL/ASSISTED WORKBENCH` in `docs/09-validation/ANIJAM_CAPABILITY_VALIDATION_2026_08_22.md`.

Rules:
- workbench receives approved Visual Work Orders by default, not authority to rewrite the full Story/Visual Plan;
- workbench-generated scene breakdown is NON-CANON unless explicitly promoted by the upstream owner;
- exact topology/spatial truth remains Blender/2D-owned;
- final timeline remains Audio/Post-owned;
- underlying provider/model is recorded when exposed; otherwise explicitly record `NOT_EXPOSED` rather than guessing;
- opaque workbench output cannot become factual/spatial authority;
- public runtime API/automation support must be separately verified before any automated integration.

Full contract: `docs/11-design-closure/GENERATIVE_WORKBENCH_ROUTING_ADDENDUM_V1.md`.

## R-2D-MOTION

Select when:
- map
- elevation profile
- dimensions
- timeline
- arrows/force/flow
- schematic mechanism

2D is a first-class explanatory medium, not a fallback for failed 3D.

## R-STILL-COMPOSITE

Select when:
- controlled still + parallax/depth is enough
- narration duration is short
- full video generation adds no explanatory value

---

# 9. No Single-SaaS Baseline

Baseline production must remain achievable with:
- Blender;
- 2D/compositing/editorial tools;
- approved assets;
- at least one valid generative cinematic route when such footage is actually needed.

No single generative SaaS—including AniJam, Higgsfield, Veo or any other named product—may become a mandatory dependency of the episode architecture.

Direct-provider capability must remain available for shots whose automation/provenance/control requirements are not satisfied by a supervised workbench.

---

# 10. Modeler Escalation Gate

Before paying a human modeler, answer:

1. Is this asset explanatory or merely decorative?
2. Can G1/G2 procedural geometry explain it?
3. Does an approved existing asset exist?
4. Can an AI mesh serve as a verified seed/proxy?
5. Will the asset be reused enough to justify manual craftsmanship?
6. Is close-up visual fidelity essential to audience trust?
7. Is manual cleanup actually cheaper than generation cleanup?

Human modeler is approved only when the expected quality/reuse value beats the manual cost.

---

# 11. Example Routing

## Venice foundation episode

- city context: existing/low-detail environment + composite
- pile field: M1 procedural cylinders/grid
- soil/water section: M1 + 2D overlays
- historical pile-driving workers: R-GENERATIVE-VIDEO; AniJam workbench or direct provider candidate
- camera descent water → mud → piles: Blender C04/C05
- close historical atmosphere: R-GENERATIVE-VIDEO

Human modeler: probably unnecessary.

## Pyramid episode

- pyramid mass/chambers: M1 procedural geometry
- cutaway: Blender
- workers / transport reconstruction: R-GENERATIVE-VIDEO
- decorative close-up only if story needs it: M2/M3/M4 by gate

Human modeler: normally unnecessary.

## Gothic cathedral ornament-focused episode

- structural nave/arches: M1 procedural
- façade establishing: M2/M3 candidate
- gargoyle/sculpture close-ups if central: M4 may be justified

Human modeler: conditional.

---

# 12. Technical Research Notes

Blender provides a Python API capable of creating animation keyframes programmatically, so deterministic camera/object animation is technically compatible with the future harness design.

AI 3D candidates are not locked:
- TRELLIS.2 supports image-to-3D and GLB extraction but has dependency/license considerations that must be reviewed for commercial workflow.
- Hunyuan3D variants support image-to-shape and some versions expose Blender-related integration, but commercial/license status must be reviewed for the exact model/version before production use.

The project must never choose an AI 3D dependency solely because it is technically free to download.

AniJam is currently classified as an optional supervised generative workbench. Its public product pages support script/image/audio-based animation, scene breakdown, consistency/motion/lip-sync/timeline workflows and multi-provider creative use, but a stable public runtime API suitable for harness automation was not verified in the 2026-08-22 review. Therefore no implementation dependency is locked.

---

# 13. Pilot Validation

Before implementing a full modeling automation layer, paper/proxy-test three asset classes:

1. **Parametric structure:** Roman aqueduct
2. **System/section:** Venetian foundation + soil/water
3. **Complex ornamental structure:** Gothic cathedral façade/detail

For each compare:
- procedural effort
- existing asset effort
- AI mesh cleanup effort
- hypothetical human modeling effort
- camera reuse
- continuity reliability
- final explanatory quality

For generative cinematic routing, use one fixed non-factual historical-activity work order to compare:
- direct provider execution;
- AniJam supervised workbench execution;
- still/composite fallback.

Measure usable-output ratio, continuity benefit, revision burden, effective cost, provenance completeness and time saved.

Only then promote a workbench beyond optional status.

---

# 14. Success Criteria

The modeling/camera strategy passes when:
- a normal episode can be planned without assuming a full-time modeler
- exact explanatory shots have deterministic spatial control
- camera moves are reproducible and reusable
- generative video is used where its uncertainty does not corrupt factual geometry
- an optional workbench cannot become a shadow Story/Visual/Post authority
- direct-provider routing remains available when automation/provenance/control requires it
- workbench attempts preserve tool/input/output/rights provenance and explicitly mark non-exposed model identity
- 2D is selected when clearer than 3D
- expensive manual modeling is justified by explicit gates
- model/tool/license provenance is recorded
- no paid camera/video platform is a mandatory dependency

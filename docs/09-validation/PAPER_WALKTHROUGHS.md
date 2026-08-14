# Validation 0.5 — Three Paper Walkthroughs

Purpose: 구현 없이 selected harness가 실제 episode를 끝까지 설명할 수 있는지 검증한다.

규칙:
- 아직 확인되지 않은 기술/역사 사실을 사실처럼 채우지 않는다.
- 여기서는 workflow, artifact handoff, gate timing, rollback만 검증한다.
- 실제 claim은 Research 단계에서 검증될 질문/가설로 표시한다.

---

# Walkthrough A — Venice Foundations

## Episode Type
Mechanism Mystery

## Candidate Central Question
“물 위에 세워진 것처럼 보이는 베네치아의 무거운 건물은 왜 가라앉지 않는가?”

## Stage 0 — Topic Brief

X-Ray value: 매우 높음
- 도시 exterior만 봐서는 foundation을 볼 수 없음
- 수면 아래 / 지층 / 기초를 reveal해야 설명 가치가 생김

Primary viewer misconception candidate:
- 건물이 물 위에 직접 떠 있거나, 단순히 진흙 위에 서 있다는 직관

Research questions:
- 실제 foundation typology는 시대/구역별로 어떻게 다른가?
- 목재 말뚝, 지층, 석재 foundation의 관계는 무엇인가?
- “나무가 물속에서 썩지 않는다”는 대중 설명은 어느 조건까지 정확한가?
- 침하/지반 문제와 foundation 안정성을 어떻게 구분할 것인가?

Topic Gate:
PASS candidate. 다만 “베네치아 전체가 하나의 동일 foundation 방식”처럼 일반화하면 위험.

## Stage 1 — Evidence Pack

Expected claim groups:
- lagoon soil/geology
- foundation construction practices
- timber behavior under low-oxygen/submerged conditions
- load distribution
- building settlement/maintenance caveats

Critical uncertainty:
- 시대/건물별 차이를 하나의 canonical model로 과도하게 단순화하지 말 것.

Research Gate condition:
대표 구조를 “typical explanatory reconstruction”으로 쓸 근거가 확보돼야 함.

## Stage 2 — Story Pack

Beat proposal:
1. Venice establishing
2. camera sinks below water
3. “진흙 위라면 왜 버티는가?”
4. ground cutaway
5. pile/foundation reveal
6. load path explanation
7. timber preservation caveat
8. settlement vs collapse distinction
9. city reassembly

Potential hook:
- 아름다운 facade보다 수면 아래를 먼저 문제로 제시

Story Gate check:
- 건축 역사 나열로 새지 않음
- question/payoff가 한 mechanism에 집중

## Stage 3 — Visual Plan

Key visual units:
- CITY_TO_WATERLINE
- WATERLINE_TO_GROUND_CUTAWAY
- FOUNDATION_LAYER_PEEL
- LOAD_PATH
- MATERIAL_DETAIL
- REASSEMBLY

Geometry decision:
**YES — geometry-backed preferred**
Reason:
- facade ↔ foundation axis relation
- pile field / footing / wall 위치 관계가 설명 핵심
- 여러 cutaway angle에서 topology 유지 필요

## Stage 4 — Asset Bible

Hard Locks:
- wall/foundation alignment
- pile field position relative to load-bearing wall
- waterline / soil layers
- canonical section direction

Soft Locks:
- facade ornament
- nearby boats

Unknown/Reconstructed:
- representative internal foundation details not universal to all Venice buildings

Asset Gate issue:
visual must clearly say “representative structure” if source does not support universal claim.

## Stage 5 — Previs

Cheap storyboard test:
- exterior → waterline → soil cutaway가 orientation을 잃지 않는가?
- pile reveal이 너무 많은 정보로 보이지 않는가?
- load path를 색/animation 하나로 이해 가능한가?

Likely revision:
한 번에 도시 전체 foundation을 보여주기보다 “대표 건물 하나를 isolate”한 뒤 다시 city-scale로 확장하는 편이 명확.

### Harness finding A1
Topic Brief에서 바로 city-scale hero object를 잡으면 Asset Bible이 과도하게 커짐.
**대표 explanatory unit을 early stage에서 정하는 필드가 필요.**

Proposed addition:
- `explanatory_unit`: whole system / representative module / component

---

# Walkthrough B — Roman Aqueduct

## Episode Type
System Journey + Historical Engineering

## Candidate Central Question
“펌프가 없던 시대에 로마의 물은 어떻게 수십 km를 이동해 도시까지 도착했는가?”

## Stage 0 — Topic Brief

X-Ray value: 높음
- 유명한 아치교만 보면 전체 수도 시스템을 오해하기 쉬움
- 실제 설명은 source → gradient → covered channel → bridge/tunnel → distribution로 이어지는 journey가 핵심

Research questions:
- 특정 수도교를 case study로 할지 로마 수도 시스템 general explainer로 할지?
- slope/gradient 수치와 유지 방식은 어떤 source를 쓸지?
- settling/distribution/maintenance를 어느 깊이까지 다룰지?
- aqueduct bridge가 전체 route에서 차지하는 비중을 어떻게 과장하지 않을지?

Topic Gate issue:
“로마 수도교”가 너무 넓다.

### Harness finding B1
Topic Gate에 **scope lock**이 반드시 필요.

Choice candidate:
- one named aqueduct/system as evidence anchor
- general mechanism with multiple examples

Director must not advance until one is selected.

## Stage 1 — Evidence Pack

Claim groups:
- water source elevation
- route survey/gradient
- covered channels
- valley crossing methods
- maintenance/access
- urban distribution

Claim-to-visual importance:
높음. gradient claim은 visual scale exaggeration 때문에 fake precision 위험.

Research Gate:
- actual gradient/elevation evidence 확보
- diagram이 scale-accurate인지 explanatory exaggeration인지 표시

## Stage 2 — Story Pack

Journey beats:
1. city faucet/fountain endpoint
2. reverse trace out of city
3. mountain/source reveal
4. “물은 스스로 내려올 뿐”이라는 simple rule
5. terrain creates obstacles
6. tunnel/bridge/channel solutions
7. maintenance/sediment problem
8. city distribution
9. full route trace

Wrong intuition:
- “거대한 아치교가 수도교 전체”라는 인상

Payoff:
- system success는 monument보다 continuous gradient/control에 있음

## Stage 3 — Visual Plan

Key actions:
- MAP_TO_ROUTE
- ELEVATION_PROFILE
- FLOW_PATH
- TERRAIN_CUTAWAY
- BRIDGE_SECTION
- TUNNEL_SECTION
- CITY_DISTRIBUTION

Geometry decision:
Mixed.
- macro route: map/elevation visualization
- representative channel: geometry-backed
- historical environment: AI reconstruction allowed

### Harness finding B2
한 episode에 Hero Object 하나라는 전제가 약함.
이 episode는 **Hero System + Hero Components** 구조가 더 적합.

Required design change:
Asset model must support:
- `hero_scope = object | system`
- system can reference multiple canonical components.

## Stage 4 — Asset Bible

Hero System:
- source
- route
- channel
- valley crossing
- urban endpoint

Hard Locks:
- flow direction
- elevation ordering
- component connection order

Visual risk:
실제 고저 차이를 화면에서 너무 작아 보이지 않게 exaggerate해야 할 수 있음.

Required field:
- `scale_treatment = true_scale | visually_exaggerated | schematic`

## Stage 5 — Previs

Check:
- map/elevation/3D scene transitions에서 viewer가 같은 물의 journey를 추적 가능한가?
- architecture detail로 들어갔다가 route context를 잃지 않는가?

Likely solution:
항상 같은 flow tracer를 semantic anchor로 유지.

### Harness finding B3
Continuity는 object geometry뿐 아니라 **semantic continuity**도 필요.

Add continuity classes:
- spatial
- object
- semantic (same water/force/person journey)
- temporal

---

# Walkthrough C — Undersea Tunnel Alignment

## Episode Type
Construction Impossible

## Candidate Central Question
“바다 양쪽에서 따로 파기 시작한 터널은 어떻게 지하에서 정확히 만나는가?”

## Stage 0 — Topic Brief

X-Ray value: 매우 높음
- 지상에서는 과정이 보이지 않음
- map + earth cutaway + survey geometry가 필수

Research questions:
- 어떤 실제 tunnel project를 anchor로 할 것인가?
- historical vs modern surveying methods
- shafts, reference networks, gyroscopic/inertial surveying 등 어떤 기술이 case에 실제 사용됐는가?
- breakthrough tolerance/error를 어떤 공식 자료에서 확인할 것인가?

Hard risk:
여러 터널 프로젝트의 기술을 한 프로젝트에 섞는 composite hallucination.

Topic Gate:
**named case study required** before claims.

### Harness finding C1
Topic Brief에 `case_anchor` 필드 필요.
General explainer라도 주요 visual sequence가 특정 real case를 사용하면 명시해야 함.

## Stage 1 — Evidence Pack

Claim groups:
- surface survey/control network
- transfer underground
- heading direction/depth
- error accumulation
- correction
- breakthrough

Research Gate hard fail:
- 다른 프로젝트 기술을 source 없이 혼합

## Stage 2 — Story Pack

Build-the-Impossible beats:
1. two shores
2. impossible question: no line of sight underground
3. surface control points
4. coordinates transferred downward
5. two headings progress
6. tiny angular error grows with distance
7. measurement/correction loop
8. final breakthrough
9. surface→underground reassembly

Stress/counterfactual:
small angle error visually amplified over long distance.

This is highly visual explanatory content.

## Stage 3 — Visual Plan

Key actions:
- MAP_TO_SECTION
- SURVEY_LINE
- SHAFT_CUTAWAY
- TUNNEL_PROGRESS
- ERROR_ANGLE_AMPLIFY
- CORRECTION
- BREAKTHROUGH

Geometry decision:
**YES for deterministic explanatory geometry.**
Reason:
- angles/coordinates/spatial meeting are explanation itself
- pure generative video would risk invalid spatial relation

AI reconstruction role:
- workers/machinery atmosphere
- historical/modern establishing shots

## Stage 4 — Asset Bible

Hero System:
- coastline/control network
- two portal/shaft points
- tunnel centerline
- depth profile

Hard Locks:
- endpoints
- heading axes
- section depth
- meeting point

Potential visual simplification:
error angle may need exaggeration.
Must label schematic scale treatment.

## Stage 5 — Previs

Check:
- viewer understands coordinate transfer without math overload?
- error amplification shot clearly demonstrates why precision matters?
- surface map and underground section preserve orientation?

Likely revision:
Use one simple 2D geometric analogy before full 3D tunnel cutaway.

### Harness finding C2
Not every explanatory visual should be 3D.
Harness must allow **2D diagram as first-class production capability**, not fallback only.

---

# Cross-Walkthrough Findings

## Finding 1 — “Hero Object” is too narrow
Need:
- Hero Object
- Hero System
- Hero Component

### Design adjustment
Rename conceptual artifact from strictly `Hero Object Bible` toward **Spatial / Asset Bible**, with hero scope inside.

## Finding 2 — Continuity has four classes
1. Object continuity
2. Spatial/orientation continuity
3. Semantic journey continuity
4. Temporal/era continuity

QA must not only count geometry errors.

## Finding 3 — Scope Lock belongs early
Topic selection without exact scope creates research explosion.

Topic Brief should include:
- central question
- explanatory unit
- case anchor
- scope exclusions

## Finding 4 — Scale Treatment must be explicit
Engineering visuals often exaggerate slopes, angles, layers, or distances for comprehension.

Every such visual should declare:
- true scale
- schematic
- exaggerated for explanation

This is part of visual truth, not mere style.

## Finding 5 — 2D diagrams are first-class
Some principles are clearer as:
- elevation profile
- simple geometry
- route map
- causal graph

before/alongside 3D.

The production capability registry must include diagram/motion graphics.

## Finding 6 — Artifact count can likely be reduced
Paper walkthroughs reveal many logical artifacts can live in fewer physical documents without losing boundaries.
See `ARTIFACT_PRUNING_REVIEW.md`.

---

# Walkthrough Verdict

Selected harness topology remains valid.

Why:
- all three cases naturally require stage rollback
- source→claim→visual lineage matters in different ways
- artifact blackboard helps multi-scale systems
- thin Director is enough for state control

But four design refinements are required before implementation:
1. Hero Object → Spatial/Asset Bible with hero scope
2. add case_anchor + explanatory_unit to Topic Brief
3. continuity classes expanded
4. scale_treatment + 2D diagram capability added

These are architecture refinements, not topology changes.
